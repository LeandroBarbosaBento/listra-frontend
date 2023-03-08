<template>
  <div class="footer">
    <v-row>
      <v-col class="company-links">
        <h2>Encontre seu veículo</h2>
        <ul>
          <li><a href="#">Encontre seu veículo</a></li>
          <li><a href="#">Lojas</a></li>
          <li><a href="#">Promoções</a></li>
          <li><a href="#">Vantagens</a></li>
          <li><a href="#">Garantia Mais</a></li>
        </ul>
      </v-col>

      <v-col class="company-links">
        <h2>A Empresa</h2>
        <ul>
          <li><a href="#">Sobre</a></li>
          <li><a href="#">Delivery</a></li>
          <li><a href="#">Aviso de privacidade</a></li>
          <li><a href="#">Blog Seminovos</a></li>
        </ul>
      </v-col>

      <v-col class="company-links">
        <h2>Atendimento</h2>
        <ul>
          <li><a href="#">Perguntas Frequentes</a></li>
          <li><a href="#">Fale Conosco</a></li>
          <li><a href="#">Pós-vendas</a></li>
        </ul>
      </v-col>

      <v-col class="company-links">
        <h2>Lojistas</h2>
        <ul>
          <li><a href="#">Acesse Seminovos Atacado</a></li>
        </ul>
      </v-col>

      <v-col class="client">
        <v-row>
          <h2>Atendimento ao cliente</h2>
        </v-row>

        <v-row class="client-contact">

          <p>0800 000 000</p>
          <button type="button" class="wpp-btn">
            <v-icon icon="mdi-whatsapp"></v-icon>
          </button>

        </v-row>

      </v-col>

      <v-col class="follow-us">
        <h2>Siga a gente</h2>
        <ul>
          <li> <a href="#" class="social-button"><v-icon icon="mdi-facebook"></v-icon></a> </li>
          <li> <a href="#" class="social-button"><v-icon icon="mdi-instagram"></v-icon></a> </li>
          <li> <a href="#" class="social-button"><v-icon icon="mdi-twitter"></v-icon></a> </li>
          <li> <a href="#" class="social-button"><v-icon icon="mdi-linkedin"></v-icon></a> </li>
        </ul>
      </v-col>

    </v-row>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.footer {
  width: 100%;
  height: 268px;
  margin-top: 148px;
  padding: 40px;
  background: #343A40CC;
}

.company-links h2 {
  font-family: Roboto;
  font-size: 18px;
  font-weight: 700;
  line-height: 21px;
  letter-spacing: 0em;
  text-align: left;
  color: white;
}

.company-links ul{
  list-style-type: none;
  margin-top: 10px;
}

.company-links ul li a{
  font-family: Roboto;
  font-size: 14px;
  font-weight: 400;
  line-height: 30px;
  letter-spacing: 0em;
  text-align: left;
  text-decoration: none;
  color: white;
}
.client {
  margin-top: -2px;
}
.client h2 {
  color: white;
  font-family: Roboto;
  font-size: 16px;
  font-weight: 400;
  line-height: 19px;
  letter-spacing: 0em;
  text-align: left;
  margin-bottom: 10px;
}

.client p {
  display: block;
  height: 42px;
  width: 128px;
  border-radius: 4px;
  background: #7D28F7;
  margin-right: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-family: Roboto;
  font-size: 16px;
  font-weight: 500;
  line-height: 16px;
  letter-spacing: 0em;
  text-align: center;

}
.client .wpp-btn{
  width: 40px;
  height: 42px;
  border-radius: 4px;
  color: white;
  background: #4AC959;
}
.follow-us {
  margin-top: -13px;
}
.follow-us h2 {
  font-family: Roboto;
  font-size: 20px;
  font-weight: 500;
  line-height: 23px;
  letter-spacing: 0em;
  text-align: left;
  color: white;
  text-align: center;
}

.follow-us ul {
  display: flex;
  justify-content: center;
  gap: 10px;
  list-style-type: none;
  margin-top: 22px;
}

.follow-us ul li {
  display: flex;
  width: 25px;
  height: 27px;

  background: #7D28F7;
  border-radius: 4px;
  align-items: center;
  justify-content: center;

}

.follow-us ul li a{
  color: white;
  text-decoration: none;
  font-size: 12px;
}
</style>
