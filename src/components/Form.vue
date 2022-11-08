<template>
    <div class="box">
        <div class="columns">
            <div
                class="column is-8"
                role="form"
                arial-label="Formulário para criação de uma nova tarefa">
                <input
                    type="text"
                    class="input"
                    placeholder="Qual tarefa deseja iniciar?" />
            </div>
            <div class="column">
                <div
                    class="is-flex is-align-items-center is-justify-content-space-between">
                    <StopWatch :seconds="seconds" />
                    <button class="button" @click="start">
                        <span class="icon">
                            <i class="fas fa-play"></i>
                        </span>
                        <span>Play</span>
                    </button>
                    <button class="button" @click="stop">
                        <span class="icon">
                            <i class="fas fa-stop"></i>
                        </span>
                        <span>Stop</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import StopWatch from './StopWatch.vue';

export default defineComponent({
    name: 'FormComponent',
    components: {
        StopWatch,
    },
    data() {
        return {
            seconds: 0,
            stopWatch: 0,
        };
    },
    methods: {
        start() {
            this.stopWatch = setInterval(() => {
                this.seconds += 1;
            }, 1000);
        },
        stop() {
            clearInterval(this.stopWatch);
        },
    },
});
</script>
