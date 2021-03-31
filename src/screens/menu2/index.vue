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
        <nb-title>Juego Matematico</nb-title>
      </nb-body>
      <nb-right />
    </nb-header>
    <nb-content>
      <image
          :style="{width: 300, height: 200,left:50}"
          :source="{uri: 'https://lh3.googleusercontent.com/uqtHTBWx2Pmlrium3h85RUG3d-tvpXB5Ma45yXbsLJFKw-9ZiKdC8O0bPj7CKy3V2ssp=w412-h220-rw'}"
        />
      <text></text>
      <text class="text-color-primary" >   Juego de Matematicas</text>
    <text class="text-secondary"></text>
    <text-input class="game"
        :style="{height: 40, width: 110,borderColor: 'yellow', borderWidth: 5,left:145}"
        v-model="a"
      /><text class="text-secondary">    
      </text>
      <text class="text-secondary">       
         Calcule el resultado de 
      </text>   <text class="text-secondary"> 
         ({{e}}+{{f}}) * {{h}}
         
      </text>
      <text class="text-secondary"> </text >
      <text class="text-secondary">  
             
      <button
        v-bind:on-press="jugar"
        title="jugar"
        color="rgb(26, 221, 235)"
        accessibility-label="jugar"
    />  ----PRESIONE----
    <text class="text-secondary"></text>
      <button
        v-bind:on-press="solucion"
        title="Resultado"
        color= "rgb(26, 221, 235)"
        accessibility-label="respuesta"
        
    /></text>
    <text class="text-secondary"> </text >
    <text class="text-secondary">
      Tu score es : {{g}}
    </text>
    <text class="text-secondary"><nb-button block :onPress="() => this.props.navigation.openDrawer()" >
        <Text>Menu</Text>
      </nb-button>
    </nb-content>
  </nb-container>
</template>
<script>
export default {
  data: function() {
            return {
                a: "",
                b:"",
                c:"",
                e:"",
                f:"",
                h:"",
                g:0,
               x1:"",
               x2:1,
                
    }
  },
  methods: {
    solucion: function() {
      this.b = this.Resp(this.a)
      this.c=this.cont(this.g)
    },
    jugar:function () {
      this.inicio(this.e,this.f)      
    },
    inicio:function (e,f,h) {
      this.e=Math.floor(Math.random() * ( 15-1 )) +1 
      this.f= Math.floor(Math.random() * ( 15-1 )) +1 
      this.h= Math.floor(Math.random() * ( 10-1 )) +1 
    },
    Resp: function(a){        
      if (this.a==((this.e+this.f)*this.h)) {       
        return alert("Excelente")       
      }
      else{       
        return alert("Pésimo")
      }
    },
    cont:function (g,x1,x2) {      
      if (this.a==((this.e+this.f)*this.h)) {
        var x3=this.x1+this.x2
        this.x2++
        this.g=x3  
        return this.g          
      }
      else{ 
        x3=0      
        this.x2=1
        this.g=x3
        return this.g

      }
      
    }
  }
}
</script>
<style>

.text-secondary{
  color: rgb(26, 221, 235);  
  text-align: center;
}
.text-color-primary {
  color: rgb(26, 221, 235);
  text-align: center;
}

</style>