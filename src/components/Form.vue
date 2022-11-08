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
                <Timer />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Timer from './Timer.vue';

export default defineComponent({
    name: 'FormComponent',
    components: {
        Timer,
    },
});
</script>
