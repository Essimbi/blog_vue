<script setup>
import { defineProps } from 'vue';

const props = defineProps(['comment']) ;

</script>

<template>
    <div class="container">
        <h6><strong>{{ props.comment.author }}</strong></h6>
        <p>{{ props.comment.content }}</p>
        <!-- <span class="text-sm ml-auto">date</span> -->
    </div>
</template>

<style scoped>
span {
    float: right;
}
</style>