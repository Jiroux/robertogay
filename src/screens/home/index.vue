<template>
  <nb-container>
    <status-bar :barStyle="'light-content'"></status-bar>
    <image-background :source="launchScreenBg" class="imageContainer">
      <view class="logoContainer" :style="stylesObj.logoContainerStyle">
        <image-background
          :source="launchscreenLogo"
          class="logo"
          :style="stylesObj.logoStyle"
        />
      </view>
      <view class="text-container">
        <nb-h3 :style="{ marginBottom: 8 }" class="text-color-white"
          >Programacion Movil</nb-h3
        >
        <nb-h3 class="text-color-white">1</nb-h3>
      </view>
      <view :style="{ marginBottom: 100 }">
        <nb-button
          :style="stylesObj.btnContainer"
          :onPress="handleLetGoBtnPress"
        >
          <nb-text> Menu</nb-text>
        </nb-button>
      </view>
    </image-background>
  </nb-container>
</template>

<script>
import { Dimensions, Platform } from "react-native";
import launchScreenBg from "../../../assets/wallpaper.png";
import launchscreenLogo from "../../../assets/vue.png";

export default {
  props: {
    navigation: {
      type: Object
    }
  },
  data() {
    return {
      launchScreenBg,
      launchscreenLogo,
      stylesObj: {
        logoContainerStyle: {
          marginTop: Dimensions.get("window").height / 8
        },
        logoStyle: {
          left: Platform.OS === "android" ? 10 : 50,
          top: Platform.OS === "android" ? 150 : 60
        },
        btnContainer: {
          backgroundColor: "#6faf98",
          alignSelf: "center"
        }
      }
    };
  },
  methods: {
    handleLetGoBtnPress() {
      this.navigation.openDrawer();
    }
  }
};
</script>

<style>
.imageContainer {
  flex: 1;
}
.text-color-primary {
  color: rgb(26, 221, 235);
  font-family: Roboto;
}
.logoContainer {
  flex: 1;
  margin-bottom: 30;
  margin-left: 45;
  
}
.logo {
  position: relative;
  width: 300;
  height: 250;
}
.text-container {
  align-items: center;
  margin-bottom: 50;
  background-color: transparent;
}
.text-color-white {
  color: rgb(26, 221, 235);
}
.button-container {
  background-color: rgb(26, 221, 235);
  align-self: center;
}
</style>
