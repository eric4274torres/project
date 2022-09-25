<template>
   <div class="principal">
        <div class="bingo">
            <!-- <img src="" alt="" width="15%" height="15%"> -->
            <h1>Bingo Verano</h1>
            <!-- <img src="" alt="" width="15%" height="15%"> -->
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
                <p>Balota</p>
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
        <button class="btn" v-on:click="numaleatorio">Estoy listo</button>
        <p>Listado de balotas</p>
        <div class="listado">
            <table>
                <tr>
                    <td>B</td>
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
                    <td>I</td>
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
                    <td>N</td>
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
                    <td>G</td>
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
                    <td>O</td>
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
        <button>Comenzar de nuevo</button>
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
            letra:null
        }
    },
    methods:{
        numaleatorio(){
            this.numero=(Array.from({ length: 75 }, (_, i) => i + 1)).sort(() => Math.random() - 0.5);
            if(this.numero>=1 && this.numero<=15)this.letra="B"
            if(this.numero>=16 && this.numero<=30)this.letra="I"
            if(this.numero>=31 && this.numero<=45)this.letra="N"
            if(this.numero>=46 && this.numero<=60)this.letra="G"
            if(this.numero>=61 && this.numero<=75)this.letra="O"
            console.log(this.letra+""+ this.numero)
        }
    }

}
</script>

<style>
.principal{
    width: 100%;
    height: 100%;
    padding: 1%;
    background-color: antiquewhite;
}
.bingo{
    margin: auto;
    margin-bottom: 1%;
    width: 35%;
    display: flex;
    justify-content: space-between;
    background-color: brown;
}
h1{
    font-size: 34px;
    margin: 0;
}
.jugadores{
    width: 90%;
    height: 40%;
    display: flex;
    justify-content: space-between;
    margin: auto;
    background-color: aqua;
}
.player,.cpu{
    width: 35%;
    border: 1px solid black;
    padding: 5px;
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
.listado{
    height: 30%;
    border: 1px solid black;
    padding: 5px;
}
.listado td{
    width: 70px;
    height: 15px;
    text-align: center;
    border: 1px solid black;
}
.image{
    background-size: 100%;
}
.balota{
    width: 20%;
    height: 50%;
    border-radius: 50%;
    margin: auto;
    background-color: azure;
    text-align: center;
}
.btn{
    width: 15%;
    height: 4%;
    font-size: 18px;
    margin: 0 42%;
    margin-top: 2%;
}
button{
    width: 20%;
    height: 5%;
    font-size: 18px;
    margin-top: 4%;
}
p{
    margin-top: 3%;
    font-size: 16px;
}
table{
    width: 100%;
    height: 100%;
    border-collapse: collapse;
}
</style>