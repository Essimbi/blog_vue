<script setup>
import { defineProps, computed } from 'vue';

const props = defineProps(['article']);
const formattedDate = computed(() => {
    let date = new Date(props.article.date);
    return date.toLocaleDateString('fr-FR');
})

</script>

<template>
    <div class="card">
        <div class="card-header">
            {{ props.article.title }}
            <!-- De {{ props.article.author }} -->
        </div>
        <div class="card-body">
            <blockquote class="blockquote mb-0">
                <p>
                    {{ props.article.content }}
                </p>
                <br />
            </blockquote>
        </div>
        <div class="card-footer text-muted text-center">
            Publié le {{ formattedDate }}
        </div>
    </div>
</template>