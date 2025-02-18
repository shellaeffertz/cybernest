<script setup>

defineProps({
    modelValue: String,
});

</script>

<template>

    <textarea
        class="w-full px-4 py-2 focus:outline-none bg-gradient-to-br from-blue-50 to-purple-50 border-b-4 border-b-gray-200 resize-none"
        @input="$emit('update:modelValue', $event.target.value)"
    ></textarea>

</template>