<template>
    <div>
    <table>
        <tr>
            <td>Nome</td>
            <td>Completada?</td>

        </tr>
        <tr v-for="(tasks, index) in tasks" :key="index">
            <td>{{ tasks.name }}</td>
            <td>{{ tasks.completed }}</td>
        </tr>
    </table>
    </div>
</template>>
<script>
export default {
    data () {
        return{
            tasks:  {name: 'Arrumar o quarto', completed: true},
                {name: 'Formatar Computador', completed: true},
                {name: 'Programar', completed: true},
                {name: 'Assistir TV', completed: true}
                }
                
        }
    }
    
}
</script>>
<style scoped>

</style>>