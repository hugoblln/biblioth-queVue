<script setup>

const props = defineProps({
    id: Number,
    title: String,
    author: String,
    cover: String,
})
</script>

<template>
    <figure class="col-lg-3 col-md-4 col-sm-6 col-12 tm-gallery-item">
        <div class="tm-gallery-item-overlay">
            <img :src="'/src/assets/img/' + cover" alt="Image" class="img-fluid tm-img-center">

        </div>
        <p class="tm-figcaption">{{ title }}</p>
    </figure>
</template>