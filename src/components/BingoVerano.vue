<template>
    <div class="principal">
        <div class="bingo">
            <!-- <img src="imagen/emoji (1).png" alt="" width="15%" height="15%"> -->
            <h1>Bingo Verano</h1>
            <!-- <img src="imagen/emoji.png" alt="" width="15%" height="15%"> -->
        </div>
        <div class="jugadores">
            <div class="player">
                <table>
                    <th>B</th>
                    <th>I</th>
                    <th>N</th>
                    <th>G</th>
                    <th>O</th>
                    <tr>
                        <td class="bordertop">12</td>
                        <td>18</td>
                        <td>41</td>
                        <td>47</td>
                        <td class="bordertopright" style="border-right: none;">61</td>
                    </tr>
                    <tr>
                        <td>7</td>
                        <td>26</td>
                        <td>39</td>
                        <td>54</td>
                        <td style="border-right: none;">70</td>
                    </tr>
                    <tr>
                        <td>4</td>
                        <td>27</td>
                        <td class="image"></td>
                        <td>49</td>
                        <td style="border-right: none;">63</td>
                    </tr>
                    <tr>
                        <td>5</td>
                        <td>23</td>
                        <td>35</td>
                        <td>58</td>
                        <td style="border-right: none;">73</td>
                    </tr>
                    <tr>
                        <td class="borderbottomletf" style="border-bottom: none;">3</td>
                        <td style="border-bottom: none;">30</td>
                        <td style="border-bottom: none;">32</td>
                        <td style="border-bottom: none;">52</td>
                        <td class="borderbottom" style="border-right: none; border-bottom: none;">75</td>
                    </tr>
                </table>
            </div>
            <div class="balota">
                <div class="blt">
                    <p>Balota<br>{{letra}}<span>{{numero}}</span></p>
                </div>
            </div>
            <div class="cpu">
                <table>
                    <th>B</th>
                    <th>I</th>
                    <th>N</th>
                    <th>G</th>
                    <th>O</th>
                    <tr>
                        <td class="bordertop">5</td>
                        <td>30</td>
                        <td>36</td>
                        <td>46</td>
                        <td class="bordertopright" style="border-right: none;">68</td>
                    </tr>
                    <tr>
                        <td>2</td>
                        <td>17</td>
                        <td>35</td>
                        <td>58</td>
                        <td style="border-right: none;">67</td>
                    </tr>
                    <tr>
                        <td>9</td>
                        <td>27</td>
                        <td class="image"></td>
                        <td>60</td>
                        <td style="border-right: none;">70</td>
                    </tr>
                    <tr>
                        <td>6</td>
                        <td>24</td>
                        <td>31</td>
                        <td>52</td>
                        <td style="border-right: none;">64</td>
                    </tr>
                    <tr>
                        <td class="borderbottomletf" style="border-bottom: none;">13</td>
                        <td style="border-bottom: none;">20</td>
                        <td style="border-bottom: none;">40</td>
                        <td style="border-bottom: none;">47</td>
                        <td class="borderbottom" style="border-right: none; border-bottom: none;">73</td>
                    </tr>
                </table>
            </div>
        </div>
        <div class="listo">
            <input type="button" value="Estoy listo" class="btn btn-light" v-on:click="numaleatorio">
        </div>
        <p>Listado de balotas</p>
        <div class="listado">
            <table>
                <tr>
                    <td class="b">B</td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                </tr>
                <tr>
                    <td class="i">I</td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                </tr>
                <tr>
                    <td class="n">N</td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                </tr>
                <tr>
                    <td class="g">G</td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                </tr>
                <tr>
                    <td class="o">O</td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                    <td></td>
                </tr>
            </table>
        </div>
        <input type="button" value="Comenzar de nuevo" class="btn btn-light">
    </div>
</template>

<script>
export default {
    name:'BingoVerano',
    data(){
        return{
            numero:0,
            numiInicial:1,
            numFinal:75,
            letra:'#'
        }
    },
    methods:{
        numaleatorio(){
            this.numero=Math.round(Math.random()*(this.numiInicial-this.numFinal)+this.numFinal);


            if(this.numero>=1 && this.numero<=15){
                this.letra='B'
            }
            if(this.numero>=16 && this.numero<=30){
                this.letra='I'
            }
            if(this.numero>=31 && this.numero<=45){
                this.letra='N'
            }
            if(this.numero>=46 && this.numero<=60){
                this.letra='G'
            }
            if(this.numero>=61 && this.numero<=75){
                this.letra='O'
            }
            console.log(this.letra+""+this.numero);
        }
    }

}
</script>

<style>
.principal{
    width: 100%;
    height: 100%;
    padding: 1%;
}
.bingo{
    margin: 0;
    margin-bottom: 2%;
    display: flex;
    align-items: center;
    justify-content: center;
    
}
h1{
    font-size: 34px;
}
.listo{
    display: flex;
    align-items: center;
    justify-content: center;
}
.jugadores{
    width: 90%;
    height: 40%;
    display: flex;
    justify-content: space-between;
    margin: auto;
}
.player,.cpu{
    width: 35%;
    padding: 10px;
    border-radius: 15px;
}
.player td, .cpu td{
    font-size: 20px;
    text-align: center;
    background-color: white;
    border-right: 1px solid black;
    border-bottom: 1px solid black;
}
.borderbottom{
    border-bottom-right-radius: 15px;
}
.bordertop{
    border-top-left-radius: 15px;
}
.borderbottomletf{
    border-bottom-left-radius: 15px;
}
.bordertopright{
    border-top-right-radius: 15px;
}
.b{
    background-color: #4ebeea;

}
.i{
    background-color: #de3935;
}
.n{
    background-color: #e8d415;
}
.g{
    background-color: #48cc76;
}
.o{
    background-color: #a557eb;
}
.b,.i,.n,.g,.o{
    font-size: 30px;
    font-weight: bolder;
}
.listado{
    height: 30%;
    border: 1px solid black;
    padding: 10px;
    border-radius: 20px;
    background-color: antiquewhite;
}
.listado td{
    width: 70px;
    height: 15px;
    text-align: center;
    border: 1px solid black;
}
.image{
    /* background-image: url(imagen/estrella.png);
    background-repeat: no-repeat;
    background-position: center; */
    background-size: 100%;
}
.balota{
    width: 20%;
    height: 47%;
    border-radius: 50%;
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #4ebeea;
    text-align: center;
}
.btn{
    font-size: 18px;
    margin-top: 2%;
}
.player{
    background-color: #4ebeea;
}
.cpu{
    background-color: red;
}
.blt{
    width: 60%;
    height: 60%;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
}
button{
    width: 20%;
    height: 5%;
    font-size: 18px;
    margin-top: 4%;
}
p{
    margin: 0;
    margin-top: 2%;
    padding: 0;
    font-size: 24px;
    
}
table{
    width: 100%;
    height: 100%;
    border-collapse: collapse;
}
th{
    font-size: 24px;
    font-weight: bolder;
    text-align: center;
}
span{
    margin-left: 10%;
}
</style>