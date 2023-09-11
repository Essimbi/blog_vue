<script setup>
    import { ref, defineProps, defineEmits } from 'vue' ;
    import axios from 'axios';

    const content = ref('') ;
    const author = ref('') ;

    const props = defineProps({
        articleId: {
            type: String,
            required: true
        }
    })

    const emits = defineEmits(['getMessage']) ;

    const handleSubmit = () => {
        let data = {
            content: content.value,
            article: props.articleId,
            author: author.value
        }

        let url = "http://localhost:3000/api/comment/"

        axios
        .post(url, data)
        .then((response) => {
        author.value= "";
        content.value="";
        emits("getMessage", response.data.message) ;
        // console.log(response) ;
        })
        .catch( (error) => console.log(error))
    }

</script>

<template>
    <div class="container mt-3">
        <form @submit.prevent="handleSubmit">
            <div class="mb-3">
                <label for="content" class="form-label">Commentaire</label>
                <textarea class="form-control" rows="3" v-model="content"></textarea>
            </div>
            <div class="mb-3">
                <label for="title" class="form-label">Auteur</label>
                <input type="text" class="form-control" placeholder="Nom de l'auteur" v-model="author">
            </div>
            <button type="submit" class="btn btn-primary">Publier</button>
        </form>
    </div>
</template>