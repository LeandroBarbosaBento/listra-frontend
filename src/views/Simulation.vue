<template>

  <div class="simulation-container">

      <h1 class="row simulation-title">Simulação de Financiamento</h1>

      <v-container class="simulation-box">
        <v-row>
          <h2 class="simulation-description">Selecione um veículo que deseja simular o financiamento</h2>
        </v-row>
        <v-row class="select-line">
          <v-select
            class="select-class align-self-center"
            bg-color="white"
            label="Selecione"
            variant="outlined"
            hide-details
            :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
          ></v-select>

          <v-btn
            rounded="pill"
            color="#7D28F7"
            class="simulation-button align-self-center"
          >
            <span>Simular</span>
          </v-btn>
        </v-row>

      </v-container>
  </div>


</template>

<script>
</script>

<style scoped>
.simulation-container {
  margin: auto;
  margin-top: 84px;
  border: 1px solid red;
  width: 95%;
}

.simulation-box{
  background: white;
  padding: 35px;
}

.select-line{
  width: 70%;
  padding: 10px;
  gap: 50px;
}
v-select{
  border: 2px solid red;
}
.simulation-button{
  width: 180px;
  padding: 0;
}
.simulation-button span{
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 900;
  font-size: 16px;
  line-height: 19px;
  text-align: center;
  color: #FFFFFF;
  text-transform: none;
}
</style>
