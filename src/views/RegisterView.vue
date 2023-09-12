<template>
    <div>
       <form>
        <label>Nome:</label>
        <input type="text" id="nome" name="nome" v-model="dataForm.nome"><br><br>

        <label>Email:</label>
        <input type="email" id="email" name="email" v-model="dataForm.email" ><br><br>

        <label>Senha:</label>
        <input type="password" id="senha" name="senha" v-model="dataForm.senha" ><br><br>

        <button type="button" @click="register()"> Criar</button>
       </form>
    </div>
</template>

<script>
import axios from 'axios' //npm install axios --save
export default {
    name: 'RegisterView',
    data(){
        return {
            dataForm: {}
        }
    },
    methods: {
        register(){//abaixoPromisse
            axios.post(`${process.env.VUE_APP_URL}register`,this.dataForm).then((response)=>{
                console.log(response.data);
            }).catch((error)=>{
                console.log(error);
            })
        }
    }
}

</script>