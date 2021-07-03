<template>
    <form>
        <label for="credencial-destinatario">Tipos de Pastas: </label>
        <div v-for="tipoPasta in tiposPasta" :key="tipoPasta.idTipoPasta">
            <input  
                type="checkbox" 
                :id="tipoPasta.idTipoPasta"
                :value="tipoPasta.idTipoPasta"
                name="tipo-pasta" 
                v-model="tipoPastaSelecionada">
            <label>{{tipoPasta.dsPasta}}</label>
        </div>
        
    </form>
</template>

<script>
    export default {
        props: ['idCredencialDestinatario'],
        data() { 
            return {
                credencialDestinatarioSelecionado: null,
                tipoPastaSelecionada: [],
                tiposPasta: 
                [
                    {
                        idTipoPasta: "1",
                        dsPasta: "Caixa de Entrada"
                    },
                    {
                        idTipoPasta: "2",
                        dsPasta: "Saida"
                    },
                    {
                        idTipoPasta: "3",
                        dsPasta: "Cancelados"
                    },
                    {
                        idTipoPasta: "4",
                        dsPasta: "Excluidos"
                    }
                ]
        }
    }
}
</script>
