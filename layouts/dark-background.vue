<script setup lang="ts">
import { computed } from 'vue'
import { resolveAssetUrl } from '../layoutHelper'

const props = defineProps({
    image: String,
})

const style = computed(() => {
    const darkOverlay = 'linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),';
    return {
        backgroundImage: `${darkOverlay}url("${resolveAssetUrl(props.image)}")`,
        backgroundRepeat: 'no-repeat',
        backgroundPosition: 'center',
        backgroundSize: 'cover',
    }
})

const overlayStyle = computed(() => {
    return {
        backgroundColor: 'rgba(0, 0, 0, 0.7)',
        zIndex: 0,
    }
})
</script>

<template>
    <div class="bg-main slidev-layout default" :style="style">
        <div class="my-auto z-10">
            <slot />
        </div>
    </div>
</template>


