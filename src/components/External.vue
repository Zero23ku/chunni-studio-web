<script setup lang="ts">

const props = defineProps({
    image: String,
    link: String
});

</script>

<template>

    <a :href="props.link" target="_blank" class="img-link">
        <img :src="props.image" class="e-img"/>
    </a>
   
</template>

<style scoped>

@media (width < 550px) {
    .e-img {
        width: 90%;
    }
}

.e-img {
    max-width: 500px;
}

.img-link {
    display: inline-block;
    transform: scale(1);
    transition: transform 0.2s ease-in-out;
}

.img-link:hover {
  transform: scale(1.2);
}

a {
    justify-content: center;
    align-items: center;
    font-size: 50px;
    color:#12163F;
    margin: 20px
}
    
</style>
