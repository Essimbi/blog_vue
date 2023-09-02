<script setup>
import { useRoute } from 'vue-router' ;
import { onMounted, ref } from 'vue' ;
import axios from 'axios' ;

import DetailsContainer from '@/components/DetailsContainer.vue' ;
import BaseHeader from '@/components/BaseHeader.vue'
import CommentContainer from '@/components/CommentContainer.vue' ;
 
const article = ref({})
const route = useRoute()
const id = route.params.id

onMounted(async () => {
    const url = "http://localhost:3000/api/article/"+id ;

    try {
        const response = await axios.get(url);
        article.value = response.data;
    } 
    catch (error) {
        console.log(error);
    }

}) ;


</script>

<template>
    <BaseHeader />
    <div class="container mb-4">
        <div class="row">
            <div class="col-sm-8">
                <h5>Detail de l'article {{ article.title }}</h5>
                <DetailsContainer :article="article" />
            </div>
            <div class="col-sm-4">
            <CommentContainer :article_id="id" />
        </div>
        </div>
    </div>
</template>