<script setup>
    import { defineProps } from 'vue' ;
    
    const props = defineProps(['article']) ;
</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title">{{ props.article.title }}</h5>
            <p class="card-text"> 
                <span>
                    <!-- Article de : {{ props.article.author }} -->
                </span>
                <small>
                    Date de publication: <strong>{{ props.article.date }}</strong>
                </small>
            </p>
            <router-link :to="'/article/' + props.article._id" class="btn btn-primary">Lire</router-link>
        </div>
    </div>
</template>