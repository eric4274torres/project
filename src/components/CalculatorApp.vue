<template>
  <form class="principal needs-validation">
    <div class="form1">
      <label>Bill</label>
      <input v-on:input="calcular(porcentaje)" v-model="bill" type="text" id="bill" />
      <label class="margin">Select Tip %</label>
      <div class="botones">
        <HelloWorld numero="5%" class="btnPorcentaje" v-on:click="calcular(5)"/>
        <HelloWorld numero="10%" class="btnPorcentaje" v-on:click="calcular(10)"/>
        <HelloWorld numero="15%" class="btnPorcentaje" v-on:click="calcular(15)"/>
        <HelloWorld numero="25%" class="btnPorcentaje" v-on:click="calcular(25)"/>
        <HelloWorld numero="50%" class="btnPorcentaje" v-on:click="calcular(50)"/>
        <input type="text" placeholder="Cusstom" class="num" id="num" v-model="agregar" v-on:keyup.enter="agregarvalor(agregar)" />
      </div>
      <div>
        <label for="" class="margin">Number of People</label>
        <input v-on:input="calcular(porcentaje)" type="text" id="number" v-model="number" />
        <!-- <div class="valid-feedback">
            Looks good!
          </div> -->
      </div>
    </div>
    <div class="form2">
      <div class="display">
        <h5>Tip Amount<br /><span class="color">/ person</span></h5>
        <h1>
          $<span id="amount">{{ amountString }}</span>
        </h1>
      </div>
      <div class="display">
        <h5>Total<br /><span class="color">/ person</span></h5>
        <h1 class="mover">
          $<span id="span">{{ totalPersonaString }}</span>
        </h1>
      </div>

      <input type="button" value="Reset" id="res" v-on:click="reset()" />
    </div>
  </form>
</template>

<script>
import HelloWorld from './HelloWorld.vue';
  
export default {
  name:'CalculatorApp',
  components:{
    HelloWorld
},
  data() {
    return {
      bill: 142.55,
      number: 5,
      porcentaje: 5,
      amountString: "0.00",
      totalPersonaString: "0.00",
      amount: 0,
      agregar: null,
    }
  },
  methods: {
    calcular(porcebtaje) {
      this.porcentaje = porcebtaje;
      this.amount = (this.bill * (porcebtaje / 100)) / this.number;
      this.amountString = this.amount.toFixed(2);
      this.totalPersonaString = (this.bill / this.number + this.amount).toFixed(2);

      if(this.bill==0 && this.number==0){
        this.amountString="0.00"
        this.totalPersonaString="0.00"
      }
    },
    agregarvalor(){
      this.amount = (this.bill * (parseInt(this.agregar )/ 100)) / this.number;
      // console.log(this.amount)
      this.amountString = this.amount.toFixed(2);
      this.totalPersonaString = (this.bill / this.number + this.amount).toFixed(2);
    },
    reset(){
      this.bill=null;
      this.number=null;
      this.amountString="0.00"
      this.totalPersonaString="0.00"
      this.agregar=null
    }
  }
}
</script>

<style scoped>
.principal {
  width: 100%;
  height: 100%;
  background-color: hsl(0, 0%, 100%);
  border-radius: 20px;
  display: flex;
  padding: 2% 2%;
}

.botones {
  height: 30%;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  border: none;
}

.form1 {
  width: 50%;
  height: 100%;
  margin-right: 2%;
  border-radius: 10px;
}

.form2 {
  width: 50%;
  background-color: hsl(183, 100%, 15%);
  margin-left: 2%;
  padding: 0% 4%;
  border-radius: 10px;
  user-select: none;

}

.display {
  width: 100%;
  display: flex;
  margin-top: 10%;
  justify-content: space-between;
}

.botones input {
  width: 100%;
  height: 100%;
  text-align: center;
  background-color: hsl(183, 100%, 15%);
  color: white;
  border-radius: 5px;
}

.margin {
  margin-top: 10%;
}

.form2 input {
  width: 100%;
  height: 15%;
  margin-top: 10%;
  text-align: center;
  border-radius: 5px;
  border: none;
  font-size: 18px;
  background-color: hsl(172, 67%, 45%);
}

.mover {
  margin-left: 5%;
}

.color {
  color: hsl(186, 14%, 43%);
  font-size: 12px;
}

.botones .num {
  padding: 0;
  background-color: hsl(189, 41%, 97%);
  color: hsl(183, 100%, 15%);
  text-align: right;
  border: none;
  outline: none;
}

#bill {
  background-image: url(../assets/icon-dollar.svg);
  background-repeat: no-repeat;
  background-position: 5% center;
  background-size: 5%;
  outline: none;
}

#number {
  background-image: url(../assets/icon-person.svg);
  background-repeat: no-repeat;
  background-position: 5% center;
  background-size: 5%;
  outline: none;
}

#res {
  font-family: "Space Mono", monospace;
  font-size: 24px;
  margin-top: 35%;
}

label {
  display: block;
  font-family: "Space Mono", monospace;
  margin-bottom: 4%;
  color: hsl(184, 14%, 56%);
}

input {
  width: 100%;
  height: 10%;
  text-align: right;
  color: hsl(183, 100%, 15%);
  font-family: "Space Mono", monospace;
  font-size: 24px;
  border-radius: 5px;
  background-color: hsl(189, 41%, 97%);
  border: none;
}

h5 {
  padding: 0;
  margin-right: 10%;
  color: hsl(0, 0%, 100%);
  margin: 0%;
  margin-top: 5%;
}

img {
  position: absolute;
  margin-top: -15%;
}

h1 {
  padding: 0;
  margin: 0;
  color: hsl(172, 67%, 45%);
  font-size: 50px;
}

.btnPorcentaje:focus {
  background-color: hsl(172, 67%, 45%);
  color: hsl(183, 100%, 15%);
}

.botones .num:focus {
  outline: 2px solid hsl(172, 67%, 45%);
}

#bill:focus,
#number:focus {
  outline: 2px solid hsl(172, 67%, 45%);
}

</style>
