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
            item-title="modelo"
            item-value="index"
            :items="carNames"
            v-model="carSelected"
          ></v-select>

          <v-text-field
            label="Qual o valor da entrada?"
            variant="outlined"
            density="comfortable"
            class="select-class align-self-center"
            hide-details
            v-model="entrada"
          >
          </v-text-field>


          <v-btn
            rounded="pill"
            color="#7D28F7"
            class="simulation-button align-self-center"
            @click="simulate"
          >
            <span>Simular</span>
          </v-btn>
        </v-row>

      </div>
  </div>

  <div class="my-container cards-info-container">
    <v-row>
      <v-col cols="12" md="3">
        <CarInfo :car="carSelectedInfo" />
      </v-col>
      <v-col cols="12" md="9">
        <CarSimulation :simulation="simulation"/>
      </v-col>
    </v-row>

  </div>

  <PageFooter />


<v-snackbar
  v-model="snackbar"
  vertical
  color="deep-purple-accent-4"
  elevation="24"
>
  <div class="text-subtitle-1 pb-2">O valor da entrada deve ser menor que o valor total do veículo</div>
  <template v-slot:actions>
    <v-btn
      color="white"
      variant="text"
      @click="snackbar = false"
    >
      Fechar
    </v-btn>
  </template>
</v-snackbar>

</template>

<script>
import api from '@/api'
import CarInfo from '@/components/CarInfo.vue'
import CarSimulation from '@/components/CarSimulation.vue'
import PageFooter from '@/components/PageFooter.vue'


export default {
  components:{
    CarInfo,
    CarSimulation,
    PageFooter,
  },
  data: () => ({
      cars: [],
      carNames: [],
      carSelected: null,
      carSelectedInfo: {
        "id": 0,
        "created_at": "0000-00-00T00:00:00.000000Z",
        "updated_at": "0000-00-00T00:00:00.000000Z",
        "foto": "https://via.placeholder.com/400x400.png/007722?text=Nenhum+Veículo+Selecionado",
        "cidade": "-",
        "marca": "-",
        "modelo": "-",
        "descricao": "Nenhum veículo selecionado",
        "ano": 0,
        "quilometragem": 0,
        "cambio": "-",
        "telefone": "-",
        "valor": 0
      },
      snackbar: false,
      entrada: 0,
      simulation: {
        valor: 0,
        entrada: 0,
      }
  }),
  created(){
    api.get('/car').then(response => {

      this.cars = response.data.data;
      this.carNames = response.data.data.map((item, index) => {
        return {
          'index': index,
          'modelo': item.modelo
        }
      })

    })
  },
  watch: {
    carSelected(carIndex) {
      this.carSelectedInfo = this.cars[carIndex]
    }
  },
  methods: {
    simulate(){
      if(this.carSelectedInfo.valor < this.entrada){
        this.snackbar = true
        this.entrada = 0
      }
      else
        this.simulation = {
          valor: this.carSelectedInfo.valor,
          entrada: this.entrada,
        }
    }
  }
}
</script>

<style scoped>

.car-information {
  gap: 28px;
}

.my-container {
  margin: auto;
  margin-top: 84px;
  width: 95%;
}

.cards-info-container{
  width: 93%;
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
  width: 80%;
  padding-top: 16px;
  gap: 25px;
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

@media only screen and (max-width: 800px) {
  .my-container {
    margin-top: 74px;
  }

  .simulation-box {
    margin-top: 15px;
    width: 100%;
  }

  .select-line{
    width: 100%;
    padding-top: 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .select-class {
    width: 100%;
  }

  .simulation-title{
    font-size: 18px;
    line-height: 21px;
    text-align: left;
    height: 21px;

  }
  .simulation-title::before{
    display: none;
  }

  .cards-info-container{
    margin-top: 15px !important;
  }
}
</style>
