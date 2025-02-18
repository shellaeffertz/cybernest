<script setup>

defineProps({
    modelValue: String,
});

</script>

<template>

    <input
        :value="modelValue"  
        class="w-full px-4 py-2 focus:outline-none bg-gradient-to-br from-blue-50 to-purple-50 border-b-4 border-b-gray-200"
        @input="$emit('update:modelValue', $event.target.value)" 
    />

</template>