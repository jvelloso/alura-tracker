<template>
    <BoxLista>
        <div class="columns">
            <div class="column is-7">{{ tarefa.descricao || 'Tarefa sem descrição'}} </div>
            <div class="column">
                <CronometroTarefa :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>

    </BoxLista>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefa'
import { defineComponent, PropType } from 'vue'
import CronometroTarefa from './CronometroTarefa.vue'
import BoxLista from './BoxLista.vue'


export default defineComponent({
    name: 'TarefaLista',
    components:{
        CronometroTarefa,
        BoxLista,
    },
    props: {
        tarefa:{
            type: Object as PropType<ITarefa>,
            required: true
                
        }
    }
})
</script>

<style scoped >

    .box{
        background: #ddaddb;
    }

</style>
