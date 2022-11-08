<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <StopWatch :seconds="seconds" />
        <button class="button" @click="start" :disabled="isStarted">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>Play</span>
        </button>
        <button class="button" @click="stop" :disabled="!isStarted">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>Stop</span>
        </button>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import StopWatch from './StopWatch.vue';

export default defineComponent({
    name: 'TimerComponent',
    components: {
        StopWatch,
    },
    data() {
        return {
            seconds: 0,
            interval: 0,
            isStarted: false,
        };
    },
    methods: {
        start() {
            this.isStarted = true;
            this.interval = setInterval(() => {
                this.seconds += 1;
            }, 1000);
        },
        stop() {
            this.isStarted = false;
            clearInterval(this.interval);
        },
    },
});
</script>
