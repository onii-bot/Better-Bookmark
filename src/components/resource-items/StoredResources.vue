<template>
    <ul>
    <resource-item
    v-for="res in resources" 
    :key="res.id" 
    :res="res"></resource-item>
  </ul>
</template>

<script>

import ResourceItem from "./ResourceItem.vue";

export default{
    name: "stored-resources",
    components: {
        ResourceItem
    },
    inject: ['resources']
}
</script>