<template>
   <Header />
   <main id="main">
      <Welcome />
      <ProjectList />
   </main>
</template>

<script>
import Header from "./components/Header.vue";
import Welcome from "./components/Welcome.vue";
import ProjectList from "./components/ProjectList.vue";

export default {
   name: "App",
   components: {
      Header,
      Welcome,
      ProjectList,
   },
};
</script>

<style lang="scss">
//! use trước, import sau
@use "@/assets/scss/colors.scss" as *;
@use "@/assets/scss/variables.scss" as *;

@import url("@/assets/scss/base.scss");

@font-face {
   font-family: "JosefinSans";
   font-weight: 400;
   font-style: normal;
   font-display: auto;
   src: local("JosefinSans"),
      url("@/assets/fonts/JosefinSans-VariableFont_wght.ttf") format("truetype");
}

body {
   &::-webkit-scrollbar {
      width: 0px;
   }

   &::-webkit-scrollbar-track {
      -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
      background-color: white;
   }

   &::-webkit-scrollbar-thumb {
      border-radius: 20px;
      background-color: $primaryColor;
   }
}

#app {
   font-family: "JosefinSans";
   -webkit-font-smoothing: antialiased;
   -moz-osx-font-smoothing: grayscale;
   text-align: center;
   color: $secondaryColor;
   min-height: 100%;
   width: 100vw;
   position: relative;
}

#main {
   z-index: 0;
}

.card {
   padding: 24px;
   background-color: white;
   box-shadow: $boxShadowCard;
   border-radius: 5px;
}

.flex {
   display: flex;

   &.jc-space-between {
      justify-content: space-between;
   }

	&.ai-center {
		align-items: center;
	}
}

a.btn,
button.btn {
   display: block;
   width: 100%;
   padding: 14px 12px 12px;
   text-align: center;
   color: white;
   border-radius: $borderRadius;
   cursor: pointer;
   transition: all 0.3s ease;

   &:hover {
      opacity: 0.8;
   }

	&.primary-btn {
		background-color: $primaryColor;
	}

   &.secondary-btn {
      background-color: $secondaryColor;
   }

   &.tertiary-btn {
      background-color: $tertiaryColor;
   }
}
</style>
