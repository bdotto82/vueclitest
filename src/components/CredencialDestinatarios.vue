<template>
    <div class="card">
        <form>
            <label for="credencial-destinatario">Destinatario: </label>
            <select name="credencial-destinatario" v-model="credencialDestinatarioSelecionado" >
                <option v-for="credencialDestinatario in credencialDestinatarios" 
                    :key="credencialDestinatario.idCredencialDestinatario" 
                    :value="credencialDestinatario.idCredencialDestinatario">
                    {{credencialDestinatario.nmDestinatario}} - {{credencialDestinatario.dsEmailDestinatario}}
                </option>
            </select>
        </form>
    </div>
    <div v-if="credencialDestinatarioSelecionado != null" class="card">
        <credencial-destinatario-tipo-pasta :is="tipoSelecionado" :key="credencialDestinatarioSelecionado" :id-credencial-destinatario="credencialDestinatarioSelecionado"/>
        <credencial-destinatario-tipo-mensagem :is="tipoSelecionado" :key="credencialDestinatarioSelecionado" :id-credencial-destinatario="credencialDestinatarioSelecionado" />
        <br>
        <button @click="salvar()">Salvar</button>
    </div>
</template>

<script>
    import CredencialDestinatarioTipoPasta from "./CredencialDestinatarioTipoPasta.vue";
    import CredencialDestinatarioTipoMensagem from "./CredencialDestinatarioTipoMensagem.vue";

    export default {
        components: {
            CredencialDestinatarioTipoPasta,
            CredencialDestinatarioTipoMensagem
        },
        props: ['idCredencialBacen'],
        data() { 
            return {

                credencialDestinatarioSelecionado: null,
                tipoSelecionado: 'credencial-destinatario-tipo-pasta',
                credencialDestinatarios: 
                [
                    {
                        idCredencialDestinatario: "1",
                        nmDestinatario: "Bruno Dotto",
                        dsEmailDestinatario: "bruno.dotto@unicre.com.br"
                    },
                    {
                        idCredencialDestinatario: "2",
                        nmDestinatario: "Mathias Dotto",
                        dsEmailDestinatario: "mathias@gmail.com"
                    }
                ]
        }
        }
    }
</script>
