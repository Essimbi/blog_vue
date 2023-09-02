<script setup>
import { defineProps } from 'vue';

const props = defineProps(['article']);
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
            Publié le {{ props.article.date }}
        </div>
    </div>
</template>