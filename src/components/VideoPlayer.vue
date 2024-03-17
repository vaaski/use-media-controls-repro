<script setup lang="ts">
import { useMediaControls } from "@vueuse/core"
import { ref } from "vue"

const props = defineProps<{
  src: string
}>()

const videoElement = ref<HTMLVideoElement>()

const { playing, currentTime, duration } = useMediaControls(videoElement, {
  src: props.src,
})
</script>

<template>
  <video ref="videoElement" controls></video>

  <span>playing: {{ playing }} {{ currentTime }} {{ duration }}</span>
</template>
