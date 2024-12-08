<template>
  <div class="home">
    <img alt="Лого" :src="logo" />
    <HelloWorld msg="Ласкаво просимо на портал" :desserts="dataDes" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import logo from "@/assets/logo.png";

export default {
  name: "HomePage",
  components: {
    HelloWorld,
  },
  data: function () {
    return {
      logo,
      dataDes: [
        { name: "Тірамісу", calories: 976 },
        { name: "Спартак", calories: 1036 },
      ],
      count: 0,
    };
  },
};
</script>
