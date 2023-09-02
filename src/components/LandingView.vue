<script setup>
    import CardContainer from './CardContainer.vue';

    import axios from 'axios' ;
    import { onMounted, ref } from 'vue';

    var articles = ref([]);

    onMounted(async () => {
        const url = "http://localhost:3000/api/article/";
        try {
            const response = await axios.get(url);
            articles.value = response.data;
        } 
        catch (error) {
            console.log(error);
        }
    })

</script>

<template>
    <section id="section-landing" class="container mb-4">
        <h5><strong>Nos articles</strong></h5>
        <div class="row">
            <div class="col-sm-3 mt-4" v-for="(article, index) in articles" :key="index">
                <CardContainer :article="article" />
            </div>
        </div>
    </section>
</template>