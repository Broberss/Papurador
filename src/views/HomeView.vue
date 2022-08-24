<script>
export default {
  data() {
    return {
      preco: 0,
      porcentagem: 0,
      pessoas: 0,
      valor_final: 0,
      valor: 0,
    };
  },

  methods: {
    calcular() {
      const preco = this.preco;
      const porcentagem = this.porcentagem;
      const pessoas = this.pessoas;
      let valor_final = 0;
      valor_final = (preco * (1 + porcentagem / 100)) / pessoas;
      document.getElementById("final").innerHTML = "R$" + valor_final;
    },
  },
};
</script>
<template>
  <div class="tudo">
    <div class="inputes">
      <label for="preco">Valor do produto</label>
      <input class="inputs" v-model="preco" id="preco" type="number" /><br />
      <label for="jorgeta">Selecione a qualidade do serviço</label>
      <select class="inputs" v-model="porcentagem" id="jorgeta">
        <option value="0" disabled>Selecione</option>
        <option value="5">O contrário de bom (5%)</option>
        <option value="10">Quase o contrário de bom (10%)</option>
        <option value="15">B (15%)</option>
        <option value="20">BB (20%)</option>
        <option value="25">BO (25%)</option>
        <option value="30">B O M(30%)</option></select
      ><br />
      <label for="preco">Quantas pessoas vão pagar</label>
      <input class="inputs" v-model="pessoas" id="pessoas" type="number" />
      <br />
      <div class="choice act" @click="calcular()">
        <i class="fa fa-angle-double-right"></i>
        <span>CALCULAR</span>
      </div>
    </div>
    <div class="resultado">
      <h3>O valor requisitado a vossa pessoa para a devida amenta é:</h3>
      <h1 id="final"></h1>
    </div>
  </div>
  <div class="papyrus">
    <img
      src="../assets/papyrus-undertale.gif"
      class="pa"
      title="El papiron"
    />
  </div>
</template>
<style>
@import url('http://fonts.cdnfonts.com/css/papyrus');
@import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");

body {
  background-color: black;
  font-family: "Papyrus";
  font-size: larger;
}

.tudo {
  color: white;
  margin: 50px;
  border: 3px solid white;
  border-radius: 8px;
  padding: 20px;
  width: 50%;
  display: inline-block;
}

.inputs {
  margin-left: 15px;
  padding: 4px;
  font-family: "Comic Sans MS";
  border-radius: 8px;
  background-color: black;
  color: #0394fc;
  border: 2px solid #0394fc;
  
}

.inputs:hover {
  color: #6beeff;
  border: 2px solid #6beeff;
}

.papyrus {
  width:40%;
  float: left;
}

.choices {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  max-width: 80rem;
  margin: 0 auto;
  padding: 1rem 0 0 0;
}

.choice {
  width: 7.5rem;
  text-align: center;
  font-size: 2rem;
  border: 2px solid #0394fc;
  padding: 0.5rem 1rem;
  transition: all 0.2s ease;
  color: #0394fc;
  margin-top: 10px;

  display: flex;
  align-items: center;
  justify-content: flex-start;
  font-family: "VT323", monospace;
}

.choice:hover {
  color: #6beeff;
  border: 2px solid #6beeff;
  cursor: grab;
  transform: scale(1.2);
}

i {
  padding-right: 0.5rem;
}

.pa{
  height: 850px;
  transition: 20s;
}
.pa:hover{
  transform: scale(1.5);
}
</style>
