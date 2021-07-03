<template>
<section>
    <header>
        <h2>Perfil de Credenciais BCCorreio</h2>
        <Credenciais/>
    </header>
</section>
</template>

<script>
 import Credenciais from './components/Credenciais.vue';

export default {
    components: {
        Credenciais
    }
}

</script>

<style>
    * {
      box-sizing: border-box;
    }

    div {
        margin: 3px 20px;
    }

    .card {
        padding: 20px;
        margin: 10px auto;
        width: 70%;
        border-radius: 10px;
        border: black solid 2px;
    }

    label {
        margin: 3px ;
        padding-left: 10px;
    }
 
    h2 {
        margin: auto;
        text-align: center;
        padding: 30px;
    }

button {
  background: #0e4f1f;
  color: white;
  font: inherit;
  border: 1.5px solid #0e4f1f;
  padding: 0.5rem;
  border-radius: 8px;
  font-weight: bold;
  cursor: pointer;
}

button:hover,
button:active {
  background: white;
  color: #0e4f1f;
}

button:focus {
  outline: none;
}
</style>