<template>
    <div class="grid grid-cols-2 w-full h-full">
        <div class="slidev-layout default" :class="props.class">
            <slot />
        </div>
        <div class="w-full w-full" :style="style"></div>
    </div>
</template>

<script setup lang="ts">
import { computed, defineProps } from 'vue'

const props = defineProps({
    image: {
        type: String,
    },
    class: {
        type: String,
    },
})

const style = computed(() => {
    return {
        backgroundImage: `url('${props.image}')`,
        backgroundRepeat: 'no-repeat',
        backgroundPosition: 'center',
        backgroundSize: 'contain',
    }
})

</script>
