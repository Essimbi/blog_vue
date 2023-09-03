<script setup>
    import { defineProps, computed } from 'vue' ;
    
    const props = defineProps(['article']) ;
    const formattedDate = computed(() => {
        let date = new Date(props.article.date) ;
        return date.toLocaleDateString('fr-FR') ;
    })

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
                    Publié le <strong>{{ formattedDate }}</strong>
                </small>
            </p>
            <router-link :to="'/article/' + props.article._id" class="btn btn-primary">Lire</router-link>
        </div>
    </div>
</template>