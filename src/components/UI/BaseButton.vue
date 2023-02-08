<template>
    <button :class="[bg, hoverbg, textcolor]" class="border rounded-lg p-2">
        <slot></slot>
    </button>
</template>

<script>
export default{
    props: {
        bg : String,
        hoverbg: String,
        textcolor: String
    }
}
</script>