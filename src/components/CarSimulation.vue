<template>
  <div class="container-simulation">

    <div>



      <v-row>
        <v-col cols="12" md="6">
          <h1 class="my-title">Valores simulados para você</h1>
          <div class="card-group">

            <v-row>
              <v-col cols="12" md="12">
                <v-card elevation="2" class="my-card">
                  <div class="card-times">
                    6x
                  </div>
                  <div class="card-value">
                    {{ seisVezes }}
                  </div>

                  <div class="card-tag">
                    <span> IPVA GRÁTIS </span>
                  </div>
                </v-card>
              </v-col>
            </v-row>

            <v-row>
              <v-col cols="12" md="6">
                <v-card elevation="2" class="my-card">
                  <div class="card-times">
                    12x
                  </div>
                  <div class="card-value">
                    {{ dozeVezes }}
                  </div>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card elevation="2" class="my-card">
                  <div class="card-times">
                    48x
                  </div>
                  <div class="card-value">
                    {{ quarentaOitoVezes }}
                  </div>
                </v-card>
              </v-col>
            </v-row>

            <v-row>
              <v-col class="contact-card" cols="12" md="12">
                <v-btn
                  rounded="pill"
                  color="#1ABB59"
                  height="40"
                  min-width="257"
                  class="align-self-center"
                  prepend-icon="mdi-whatsapp"
                >
                  <span class="button-text">Falar com consultor</span>
                </v-btn>

                <span class="contact-number">(31) 3441-0240</span>
              </v-col>
            </v-row>
          </div>
        </v-col>

      </v-row>
    </div>

  </div>

</template>

<script>
export default {
  props: ['simulation'],
  data: () => ({

  }),
  computed: {
    seisVezes() {
      let value;
      value = ( this.simulation.valor + this.simulation.valor * 0.1247 - this.simulation.entrada ) / 6

      return value.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })
    },
    dozeVezes() {
      let value;
      value = ( this.simulation.valor + this.simulation.valor * 0.1556 - this.simulation.entrada ) / 12

      return value.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })
    },
    quarentaOitoVezes() {
      let value;
      value = ( this.simulation.valor + this.simulation.valor * 0.1869 - this.simulation.entrada ) / 48

      return value.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })
    }
  }
}
</script>

<style>
.container-simulation{
  background-color: white;
  padding: 33px;
}

.my-title{
  font-family: Roboto;
  font-size: 20px;
  font-weight: 700;
  line-height: 23px;
  letter-spacing: 0em;
  text-align: left;
  color: #444444;
  margin-bottom: 36px;
  position: relative;
}

.my-title::before {
    content: "";
    display: block;
    width: 55px;
    height: 3px;
    background: #7D28F7;
    position: absolute;
    top: 38px;
    left: 0px;
}

.card-group{
  gap: 10px;
}

.my-card{
  padding: 16px;
  position: relative;
}

.card-times {
  text-transform: uppercase;
  color: #444444;
  font-family: Roboto;
  font-size: 16px;
  font-weight: 700;
  line-height: 19px;
  letter-spacing: 0em;
  text-align: left;

}
.card-value{
  color: #7D28F7;
  font-family: Roboto;
  font-size: 25px;
  font-weight: 700;
  line-height: 29px;
  letter-spacing: 0em;
  text-align: left;
}

.card-tag{
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 6px 9px;
  gap: 7px;
  width: 100px;
  height: 24px;

  position: absolute;
  left: 78.21%;
  right: 0%;
  top: 29.21%;
  bottom: 43.82%;

  background: #7D28F7;
  border-radius: 16px 0px 0px 16px;
}

.card-tag span {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 14px;
  color: #FFFFFF;
}

.contact-card {
  color: white;
}
.contact-number{
  margin-left: 16px;
  color: #444444;
  font-family: Roboto;
  font-size: 15px;
  font-weight: 700;
  line-height: 18px;
  letter-spacing: 0em;
  text-align: left;

}

.button-text{
  font-family: Roboto;
  font-size: 16px;
  font-weight: 900;
  line-height: 19px;
  letter-spacing: 0em;
  text-align: center;

}

@media only screen and (max-width: 800px) {

  .container-simulation{
    background-color: white;
    padding: 10px;
    padding-top: 37px;
    border-radius: 4px;
    box-shadow: 0px 3px 1px -2px var(--v-shadow-key-umbra-opacity, rgba(0, 0, 0, 0.2)), 0px 2px 2px 0px var(--v-shadow-key-penumbra-opacity, rgba(0, 0, 0, 0.14)), 0px 1px 5px 0px var(--v-shadow-key-penumbra-opacity, rgba(0, 0, 0, 0.12))
  }

  .my-title {
    display: none;
  }

  .card-group {
    padding: 0;
    gap: 0;
  }

  .card-group .v-row{
    width: 100%;
    margin: 0 !important;
    padding: 0;
  }

  .card-group .v-row .v-col-12 {
    padding: 0;
  }

  .my-card {
    width: 100%;
    margin-bottom: 12px;
  }

  .card-tag {
    left: 70.21%;
    right: 0%;
    top: 29.21%;
    bottom: 43.82%;
  }

  .contact-card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 16px;
    margin-top: 18px;
    margin-bottom: 32px;
  }

  .contact-number {
    margin: 0;
    text-align: center;
  }


}
</style>
