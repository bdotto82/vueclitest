<template>
    <div class="card">
    <form @submit.prevent="submitData">
        <label for="credencial">Credencial: </label>
        <select name="credencial" v-model="credencialSelecionada" @change="alterouCredencial" >
            <option v-for="credencial in credenciais" 
                :key="credencial.idCredencialBacen" 
                :value="credencial.idCredencialBacen">
                {{credencial.cdCooperativa}} - {{credencial.nmUsuario}}
            </option>
        </select>
    </form>
    </div>
    <credencial-destinatarios  v-if="credencialSelecionada != null" :key="credencialSelecionada" :id-credencial-bacen="credencialSelecionada"></credencial-destinatarios>
</template>

<script>
    import CredencialDestinatarios from "./CredencialDestinatarios.vue";

    export default {
        components: {
            CredencialDestinatarios
        },
        data() { 
            return {
                credencialSelecionada: null,
                credenciais: 
                [
                    {
                        idCredencialBacen: "1",
                        nmUsuario: "Usuario 1",
                        cdCooperativa: "9008"
                    },
                    {
                        idCredencialBacen: "2",
                        nmUsuario: "Usuario 2",
                        cdCooperativa: "27"
                    }
                ]
        }}
    }
</script>

<style>
 

</style>