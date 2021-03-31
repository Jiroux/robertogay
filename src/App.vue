<template>
  <root>
    <app-navigation></app-navigation>
  </root>
  
</template>

<script>
import {
  createAppContainer,
  createStackNavigator,
  createDrawerNavigator
} from "vue-native-router";
import { Root } from "native-base";
import HomeScreen from "./screens/home/index.vue";
import SideBarScreen from "./screens/sidebar/index.vue";
import menu1 from "./screens/menu1/";
import nuevo from "./screens/last/nuev"
import menu2 from "./screens/menu2/";
import ecuacion2do from "./screens/ecuacion2dogrado/index"
import presion from "./screens/presion/index"

const Drawer = createDrawerNavigator(
  {
    Home: { screen: HomeScreen },
    menu1: { screen: nuevo },
    menu2: { screen: menu2 },
    ecuacion: {screen: presion},
  },
  {
    initialRouteName: "Home",
    contentOptions: {
      activeTintColor: "rgb(26, 221, 235)"
    },
    contentComponent: SideBarScreen
  }
);

const AppNavigation = createAppContainer(
  createStackNavigator(
    {
      Drawer: { screen: Drawer }
     
    },
    {
      initialRouteName: "Drawer",
      headerMode: "none"
    }
  )
);
export default {
  components: { Root, AppNavigation }
};
</script>
