<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?" name="" id="">
            </div>
            <div class="column">
                <div class="is-flex is-align-items-center is-justify-content-space-between">
                    <section>
                        <strong>{{tempoDecorrido}}</strong>
                    </section>
                    <button class="button" @click="iniciarTimer">
                        <span class="icon">
                            <i class="fas fa-play"></i>
                        </span>
                        <span>play</span>
                    </button>
                    <button class="button" @click="pararTimer">
                        <span class="icon">
                            <i class="fa fa-stop"></i>
                        </span>
                        <span>stop</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue';

export default defineComponent({
    name: 'TimeForm',
    data(){
        return {
            tempoSegundos: 0,
            timer: 0
        }
    },
    computed: {
        tempoDecorrido(): string{
            return new Date(this.tempoSegundos * 1000).toISOString().substr(11,8);
        }
    },
    methods: {
        iniciarTimer(){
            console.log("timerStart");
            this.timer = setInterval(() => {
                this.tempoSegundos += 1;
                console.log(this.tempoSegundos);
            }, 1000);
        },
        pararTimer(){
            clearInterval(this.timer);
        }
    }
});

</script>
