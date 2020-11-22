<template>
  <div>
    <div class="mobile_site">
      <component :is="$router.currentRoute.value.path == '/' ? 'LoginLayout': 'LayoutMobile'">
          <router-view />
      </component>
    </div>
    <div class="desktop_site">
       <component :is="$router.currentRoute.value.path == '/' ? 'LoginLayout': 'LayoutDesktop'">
          <router-view />
      </component>
    </div>
  </div>
</template>
<script>
import LayoutMobile from "@/components/HeaderMobile";
import LayoutDesktop from "@/components/HeaderDesktop";
import LoginLayout from "@/components/Login";
export default {
  mounted(){
    console.log("route",this.$router)
  },
  components: {
    LayoutMobile,
    LayoutDesktop,
    LoginLayout,
  },
};
</script>
<style>
@media screen and (min-width:768px){
  .mobile_site{
    display: none;
  }
  .desktop_site{
    display: block;
  }
}
@media screen and (max-width: 767px){
  .mobile_site{
    display: block;
  }
  .desktop_site{
    display: none;
  }
}

</style>
