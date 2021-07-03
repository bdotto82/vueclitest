<template>
    <form>
        <label for="credencial-destinatario">Tipos de Mensagens: </label>
        <div v-for="tipoMensagem in tiposMensagem" :key="tipoMensagem.idTipoMensagem">
            <input  
                type="checkbox" 
                :id="tipoMensagem.idTipoMensagem"
                :value="tipoMensagem.idTipoMensagem"
                name="tipo-mensagem" 
                v-model="tipoMensagemSelecionada">
            <label>{{tipoMensagem.dsTipoMensagem}}</label>
        </div>
        
    </form>
</template>

<script>
    export default {
        props: ['idCredencialDestinatario'],
        data() { 
            return {
                tipoMensagemSelecionada: [],
                tiposMensagem: 
                [
                    {
                        idTipoMensagem: "1",
                        dsTipoMensagem: "AVISO"
                    },
                    {
                        idTipoMensagem: "2",
                        dsTipoMensagem: "CIRCULAR"
                    },
                    {
                        idTipoMensagem: "3",
                        dsTipoMensagem: "OFICIO"
                    },
                    {
                        idTipoMensagem: "4",
                        dsTipoMensagem: "NOTICIA"
                    }
                ]
        }
    }
    }
</script>
