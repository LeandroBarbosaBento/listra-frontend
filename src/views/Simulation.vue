<template>

  <div class="my-container">

      <h1 class="row simulation-title">Simulação de Financiamento</h1>

      <div class="simulation-box">
        <v-row>
          <h2 class="simulation-description">Selecione um veículo que deseja simular o financiamento</h2>
        </v-row>
        <v-row class="select-line">
          <v-select
            class="select-class align-self-center"
            bg-color="white"
            label="Selecione"
            variant="outlined"
            density="comfortable"
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

      </div>
  </div>

  <div class="my-container">
    <h1>INFORMAÇÕES DO VEÍCULO E PARCELAMENTO</h1>
  </div>


</template>

<script>
</script>

<style scoped>
.my-container {
  margin: auto;
  margin-top: 84px;
  width: 95%;
}

.simulation-title {
  font-family: Roboto;
  font-size: 32px;
  font-weight: 700;
  line-height: 38px;
  letter-spacing: 0em;
  text-align: left;
  color: #444444;
  height: 38px;
  position: relative;
}

.simulation-title::before {
    content: "";
    display: block;
    width: 55px;
    height: 3px;
    background: #7D28F7;
    position: absolute;
    top: 50px;
    left: 0px;
}

.simulation-box{
  background: white;
  padding: 45px;
  margin: 0 auto;
  margin-top: 42px;
  width: 98%;
}

.simulation-description {
  font-family: Roboto;
  font-size: 18px;
  line-height: 21px;
  letter-spacing: 0em;
  text-align: left;
  color: #444444;
}

.select-line{
  width: 45%;
  padding-top: 16px;
  gap: 25px;
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
