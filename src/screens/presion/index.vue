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
        <nb-title>Generador de contraseñas</nb-title>
      </nb-body>
      <nb-right />
    </nb-header>
    <nb-content>
        <image
          :style="{width: 300, height: 200,left:50}"
          :source="{uri: 'https://www.softzone.es/app/uploads-softzone.es/2017/01/password.jpg'}"
        />
    
    <text class="text-secondary"> </text ><text class="text-secondary"> </text >
    <text class="text-secondary"> </text >
        <text class="text-secondary"><text></text>
           <button
        v-bind:on-press="jugar"
        title="Generar"
        color="rgb(26, 221, 235)"
        accessibility-label="jugar"
    />    
    </text>    
    <text class="text-secondary">
        
    </text >
    <text-input class="game"
        :style="{height: 40, width: 220,borderColor: 'yellow', borderWidth: 1,left:100}"
        v-model="x"
      /><text class="text-secondary"> </text >
        <text class="text-secondary">
      <button
        v-bind:on-press="solucion"
        title="Limpiar"
        color= "rgb(26, 221, 235)"
        accessibility-label="respuesta"
        
    /> </text ><text class="text-secondary">
        
    </text ><text class="text-secondary">
        
    </text >
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
                e:"",
                f:"",
                h:"",
                x:"",
    }
  },
  methods: {
    solucion: function() {
      this.b = this.Resp(this.a)
    },
    jugar:function () {
      this.inicio(this.e,this.f)      
    },
    inicio:function (e,f) {
        var characters= 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789/*-.-,+`´¡¿ª!"·$%&/()=?';
        var charactersLength = characters.length;
        for ( var i = 0; i < charactersLength-60; i++ ) {
            this.x += characters.charAt(Math.floor(Math.random() * charactersLength));
        }
        
    },
    Resp: function(a){    
      this.x=''
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