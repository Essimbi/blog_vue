<script setup>
import { ref } from 'vue' ;

import ArticleForm from '@/components/forms/ArticleForm.vue' ;

const response = ref('') ;


const getMessage = (message) => {
    response.value = message ;
    alert(response) ;
}

</script>

<template>
    <div class="container mt-4 mb-4">
        <h5>Rédaction d'un nouvel article article</h5>
        <ArticleForm :getMessage="getMessage" />
    </div>
</template>