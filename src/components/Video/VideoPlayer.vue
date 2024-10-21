<script setup>
    const props = defineProps({
        videosrc: String,
    });
</script>

<template>
    <div class="player">
        <video autoplay muted :src="videosrc"></video>
        <div class="player__controls">
            <a href="#" @click.prevent="$emit('prefVideo')">⬆️</a>
            <a href="#" @click.prevent="$emit('nextVideo')">⬇️</a>
        </div>
    </div>
</template>

<style scoped>
    video {
       max-height: 100vh;
    }
    .player {
        background-image: url('/thumb.png');
        background-repeat: no-repeat;
        background-size: cover;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 2em;
    }

    .player__controls {
        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 10px;

    }
</style>
