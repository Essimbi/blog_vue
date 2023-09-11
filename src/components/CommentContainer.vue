<script setup>
import { defineProps, ref, onMounted } from 'vue';
import axios from 'axios';

import CommentForm from './forms/CommentForm.vue';
import CommentView from './CommentView.vue' ;

const props = defineProps(['article_id']);
const comments = ref([]);
const response = ref('') ;

onMounted( async () => {
    const url = "http://localhost:3000/api/comment/article/" + props.article_id;
    await axios
        .get(url)
        .then((response) => {
            comments.value = response.data;
        })
        .catch((error) => console.log(error))
});

const getMessage = (message) => {
    response.value = message ;
    alert(response.value) ;
}

</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title"><b>Commentaires sur l'article</b></h5>
            <div class="row">
                <div class="card card p-2 mt-1" v-for="(comment, index) in comments" :key="index">
                    <CommentView :comment="comment" />
                </div>
            </div>
        </div>
    </div>
    <CommentForm :articleId="props.article_id" @getMessage="getMessage" />
</template>