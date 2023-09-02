<script setup>
    import { defineProps, ref, onMounted } from 'vue';
    import axios from 'axios';

    const props = defineProps(['article_id']) ;
    const comments = ref([]) ; 

    onMounted(  () => {
        const url = "http://localhost:3000/api/comment/article/"+props.article_id ;
        axios
    .get(url)
    .then((response) => {
        comments.value = [...response.data] ;
    })
    .catch( (error) => console.log(error))
    }) ;

</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title">Commentaires sur l'article</h5>
            <div>
                
            </div>
        </div>
    </div>
</template>