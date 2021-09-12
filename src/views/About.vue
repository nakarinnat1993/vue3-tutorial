<template>
  <div class="about px-4">
    <h1>เกี่ยวกับเรา</h1>
    <p>{{ email }}</p>
    <a :href="googleUrl">Google</a>
    <img :src="imgUrl.url" :alt="imgUrl.alt" v-if="isShow" />
    <br />
    <button class="btn btn-info" @click="greet">Click Me!</button>
    <br />
    <Logo />
  </div>
</template>

<script>
import Logo from "../components/Logo.vue";
import { ref, reactive, onMounted, onUnmounted } from "vue";
export default {
  name: "About",
  components: {
    Logo,
  },
  setup() {
    const email = ref("cct@gmail.com");
    const googleUrl = ref("https://google.com");
    const imgUrl = reactive({
      url: "https://via.placeholder.com/100",
      alt: "My Image",
    });
    const isShow = ref(false);
    const file = ref(null);


    onMounted(() => {
      // alert("Hello About Page");
    });
    onUnmounted(() => {
      // alert("Bye About Page");
    });

    const greet = () => {
      // alert("Hello Vue3");
      email.value = "john@gmail.com";
      // isShow.value = true;
      isShow.value = !isShow.value; //toggle
    };

    return { email, googleUrl, imgUrl, isShow, greet, file };
  },
};
</script>

<style scoped>
.about {
  color: red;
}
</style>
