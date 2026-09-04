<script setup lang="ts">

const props = defineProps({
    icon: String,
    link: String
});

</script>

<template>

    <a :href="props.link" target="_blank" class="icon-link">
        <i :class="['fa-brands', props.icon]"></i>
    </a>
   
</template>

<style scoped>

.icon-link {
    display: inline-block;
    transform: scale(1);
    transition: transform 0.2s ease-in-out;
}

.icon-link:hover {
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
