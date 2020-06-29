<template>
    <div>
                
        <h4> Aluno: Gabriel Fernando Tochio</h4>
        <h4> Professor: Jaime Filho</h4>
        <h4>  RA: 18.0109-1</h4>
        <h1 v-text="title"></h1>
        <form @submit.prevent="onSubmit">
            <input type="text" placeholder="Informe o Cep:" v-model="cep">
            <button type="submit">Buscar Cep</button>
        </form>
        <div v-if="preloader">
            <img src="../assets/preloader.gif" alt="Carregando...">
        </div>
        <div v-if="error != ''">
            {{error}}
        </div>

        <div v-show="address.localidade != '' ">
           <p><b>logradouro..:</b>{{ address.logradouro }}</p>
           <p><b>Bairro......:</b>{{ address.bairro }}</p>
           <p><b>Cidade......:</b>{{ address.localidade }}</p>
           <p><b>Estado......:</b>{{ address.uf }}</p>
           <p><b>CEP.........:</b>{{ address.cep }}</p>
            
        </div>
    </div>


</template>
<script>
export default {
    data(){
        return{
            title: 'Buscar Cep',
            cep: '',
            address: {
                localidade:''
            },
            preloader: false,
            error: ''
        }
    }, methods:{
        onSubmit (){
           this.preloader = true
           this.$http     
           .get(`https://viacep.com.br/ws/${this.cep}/json/`) 
           .then( response =>{
               this.address = response.body
           },error =>{
               console.log(error)

               this.error = 'Cep Errado'
            } )
           .finally(() =>{
               this.preloader = false
           })
        }
    }
    
}
</script>
<style scoped>

</style>