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
                    <section>
                        <strong>{{ timer }}</strong>
                    </section>
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
export default defineComponent({
    name: 'FormComponent',
    data() {
        return {
            seconds: 0,
            stopWatch: 0,
        };
    },
    computed: {
        timer(): string {
            return new Date(this.seconds * 1000)
                .toISOString()
                .substring(11, 19);
        },
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
