<template>
<li>
    <base-card>
        <header class="flex justify-between items-center">
            <h3 class="font-bold text-2xl">{{ res.title }}</h3>
            <base-button bg="bg-red-700" hoverbg="hover:bg-red-600" textcolor="text-white">Delete</base-button>
        </header>
    
    <p>{{ res.description }}</p>
    <nav>
        <a class="hover:underline text-yellow-600" :href="res.link">View Resource</a>
    </nav>
</base-card>
</li>
</template>


<script>


export default{
    name: "resource-item",
    props: {
        res : Object
    }
}

</script>