<template>
  <nb-container :style="{ backgroundColor: 'rgb(109, 109, 109)' }">
    <nb-header>
      <nb-left>
        <nb-button
          transparent
          :onPress="() => this.props.navigation.openDrawer()"
        >
          <nb-icon name="menu" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Areas y Perimetros</nb-title>
      </nb-body>
      <nb-right />
    </nb-header>

    <nb-content> 
      <text class="text-color-primary" >Calculo de Area y Perimetro triangulo </text>
      <text class="text-secondary"> </text>
    <text class="text-secondary"> Base</text>
    <text-input
        :style="{height: 40, width: 100, borderColor: 'yellow', borderWidth: 2,left:145}"
        v-model="a"
      />
      <text class="text-secondary"> </text>
      <text class="text-secondary"> Altura</text>
    <text-input
        :style="{height: 40, width: 100, borderColor: 'yellow', borderWidth: 2,left:145}"
        v-model="b"
      />  <text></text>
      <text class="text-secondary"> 
      <button
        v-bind:on-press="solucion"
        title="calcular"
        color="rgb(26, 221, 235)"
        accessibility-label="trianguloArea"
    />    
      </text>
    <text class="text-secondary"> 
      Solucion= {{d}}</text>
    <text></text>
    <text class="text-color-primary" >Calculo de Area y perimetro cuadrado</text>
    <text class="text-secondary"> </text>
    <text class="text-secondary"> Lado</text>
    <text class="text-secondary"> </text>
    <text-input
        :style="{height: 40, width: 100, borderColor: 'yellow', borderWidth: 2,left:145}"
        v-model="g"
      /><text></text>
      <text class="text-secondary"> 
      <button 
        v-bind:on-press="solucion2"
        title="calcular"
        color="rgb(26, 221, 235)"
        accessibility-label="cuadradoAreaPerimetro"
    />    </text>
    <text class="text-secondary"> 
      Solucion= {{f}}</text>
    <text></text>
    <text class="text-color-primary" >Calculo de Area y Perimetro Rectangulo</text>
    <text class="text-secondary"> </text>
    <text class="text-secondary"> Base</text>
    <text class="text-secondary"> </text>
    <text-input
        :style="{height: 40, width: 100, borderColor: 'yellow', borderWidth: 2,left:145}"
        v-model="h"
      />
      <text class="text-secondary"> Altura</text>
      <text class="text-secondary"> </text>
      <text-input
        :style="{height: 40, width: 100, borderColor: 'yellow', borderWidth: 2,left:145}"
        v-model="i"
      /><text></text>
      <text class="text-secondary"> 
      <button 
        v-bind:on-press="solucion3"
        title="calcular"
        color="rgb(26, 221, 235)"
        accessibility-label="rectanguloArea"
    />    </text>
    <text class="text-secondary"> 
      Solucion= {{j}}</text>
    <text></text>
    <text class="text-color-primary" >Calculo de Area y Perimetro Circulo</text>
    <text class="text-secondary"> </text>
    <text class="text-secondary"> Diametro</text>
    <text class="text-secondary"> </text>
    <text-input
        :style="{height: 40, width: 100, borderColor: 'yellow', borderWidth: 2,left:145}"
        v-model="k"
      />
      <text></text>
      <text class="text-secondary">
       
      <button 
        v-bind:on-press="solucion4"
        title="calcular"
        color="rgb(26, 221, 235)"
        accessibility-label="circulo"
    />    </text>
    <text class="text-secondary"> 
      Solucion= {{l}}</text>
    <text></text>
    </nb-content>
  </nb-container>
</template>
<script>
    export default {
        data: function() {
            return {
                a: "",
                b: "",
                c: "",
                d: "",
                f:"",
                g:"",
                h:"",
                i:"",
                j:"",
                k:"",
                l:"",
                m:"",
            };
        },
          methods: {
        solucion: function() {
            this.d = this.EcuSolt(this.a,this.b,this.c)
        },
        solucion2: function() {
            this.f=this.CuadSolt(this.g)
        }, solucion3: function() {
            this.j=this.CuadSolt(this.h,this.i)
        }, solucion4: function() {
            this.l=this.circulo(this.k)
        },
        EcuSolt: function(a,b,c){
          var message = ""
          var validchar = /([+-]?(?=\.\d|\d)(?:\d+)?(?:\.?\d*))(?:[eE]([+-]?\d+))?/;
          var validate = a.match(validchar) && b.match(validchar) && c.match(validchar)? true : false;
          var x1 = ((this.a*this.b)/2)
          var x2=((this.a+this.b+this.c))
          message = `El valor del Area es = ${x1} y el Perimetro es =${x2}`         
          return message
        },
        CuadSolt:function (g) {
          var message = ""
          var x1=(this.g*this.g)
          var x2=(this.g*4)
          message = `El valor del Area es = ${x1} y el perimetro es = ${x2}`
          return message;
        },
        CuadSolt2:function (h,i) {
          var message = ""
          var x1=(this.h*this.i)
          var x2=(2*(this.h+this.i))
          message = `El valor del Area es = ${x1} y el Perimetro es = ${x2}`
          return message;
        },
        circulo:function (k) {
          var message = ""
          var x1=(this.k*Math.PI)
          var x2=(Math.PI*(this.k/2))
          message = `El valor del Area es = ${x2} y el Perimetro es = ${x1}`
          return message;
        }
      }
        
    }
    
</script>

<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-secondary{
  color:"rgb(26, 221, 235)";
  text-align: center;
}
.text-color-primary {
  color: "rgb(26, 221, 235)";
  text-align: center;
}
</style>
