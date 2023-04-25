<script setup lang="ts">
import { computed } from 'vue'
import { resolveAssetUrl } from '../layoutHelper'

const props = defineProps({
    image: String,
})

const style = computed(() => {
    return {
        backgroundImage: `url("${resolveAssetUrl(props.image)}")`,
        backgroundRepeat: 'no-repeat',
        backgroundPosition: 'center',
        backgroundSize: 'cover',
    }
})

const overlayStyle = computed(() => {
    return {
        backgroundColor: 'rgba(0, 0, 0, 0.7)',
        zIndex: 1,
    }
})
</script>

<!--<div class="bg-main slidev-layout default" :style="style">-->
<!--<div class="my-auto h-full">-->
<!--    <slot />-->
<!--</div>-->
<!--</div>-->

<template>
    <div class="bg-main slidev-layout default" :style="style">
        <div class="dark-overlay absolute inset-0" :style="overlayStyle"></div>
        <div class="my-auto z-10">
            <slot />
        </div>
    </div>
</template>

