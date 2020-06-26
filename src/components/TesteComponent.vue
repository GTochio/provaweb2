<template>
    <div>
        <p>Teste</p>
        <form-component></form-component>
        <h2> {{ msg }}</h2>
    </div>
</template>

<script>
import FormComponent from './FormComponent'
export default{
    data(){
        return{
            msg: 'Curso JaimeVue.js'
        }
    },
    components:{
        FormComponent
    }

}
</script>
<style >
p{color: red;}
</style>