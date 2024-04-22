<script setup>

import { ref, onMounted, computed } from 'vue'
import useAPI from '@/composables/useAPI';

const { api } = useAPI()

const keyword = ref('')
const ingredients = ref([])

onMounted(() => {
    api.get('list.php?i=list')
        .then(({ data }) => {
        ingredients.value = data.meals
    })
})

</script>

<template>
    
</template>