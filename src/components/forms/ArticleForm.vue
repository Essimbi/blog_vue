<script setup>
import { ref, defineEmits } from 'vue' ;
import axios from 'axios' ;

// const props = defineProps({
//     getMessage: Function
// })

const emits = defineEmits(['getMessage']) ;

const title = ref('') ;
const author = ref('') ;
const content = ref('') ;
const date = new Date() ;

const handleSubmit = () => {
    const url = "http://localhost:3000/api/article/" ;
    axios
    .post(url, {
      title: title.value,
      content:  content.value,
      date:   date,
      author: author.value
    })
    .then((response) => {
        title.value = "" ;
        author.value= "";
        content.value="";
        // props.getMessage(response.data.message) ;
        emits("getMessage", response.data.message) ;
    })
    .catch( (error) => console.log(error))
}

</script>

<template>
    <div class="container">
        <form @submit.prevent="handleSubmit">
            <div class="mb-3">
                <label for="title" class="form-label">Titre de l'article</label>
                <input type="text" class="form-control" placeholder="Titre de l'article" v-model="title">
            </div>
            <div class="mb-3">
                <label for="title" class="form-label">Auteur</label>
                <input type="text" class="form-control" placeholder="Nom de l'auteur" v-model="author">
            </div>
            <div class="mb-3">
                <label for="content" class="form-label">Contenu</label>
                <textarea class="form-control" rows="15" v-model="content"></textarea>
            </div>
            <button type="submit" class="btn btn-primary">Publier</button>
        </form>
    </div>
</template>