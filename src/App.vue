<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>
    <button @click="setAge">Set Age</button>
    <!-- <h2>{{ name }}</h2>
    <h3>{{ age }}</h3> -->
  </section>
</template>

<script>
// import { ref } from 'vue';
import { reactive, ref } from 'vue';
// import { reactive, ref, toRefs } from 'vue';
export default {
  setup() {
    const uName = ref('Shahrokh');
    // const user = ref({
    //   name: 'Shahrokh',
    //   age: '28'
    // });
    console.log(uName);
    const user = reactive({
      name: 'Shahrokh',
      age: '28'
    });

    // setTimeout(function() {
    //   // uName.value = 'Elmi';
    //   (user.value.name = 'elmi'), (user.value.age = '29');
    // }, 2000);
    // setTimeout(function() {
    //   // uName.value = 'Elmi';
    //   (user.name = 'elmi'), (user.age = '29');
    // }, 2000);
    const setNewAge = function() {
      user.age = 30;
    };

    // const userRefs = toRefs(user);

    return { user: user, setAge: setNewAge };
    // return { user: user, name: userRefs.name, age: userRefs.age };
    // return { userName: uName };
  }
  // data() {
  //   return {
  //     userName: 'Maximilian',
  //   };
  // },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
