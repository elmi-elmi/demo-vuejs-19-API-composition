<template>
  <h2>{{ userName }}</h2>
  <h3>{{ age }}</h3>
</template>

<script>
import {
  computed,
  inject,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted
} from 'vue';
export default {
  props: ['lastName', 'firstName'],
  setup(props) {
    const userName = computed(function() {
      return props.firstName + ' ' + props.lastName;
    });

    const age = inject('userAge');

    onBeforeMount(function() {
      console.log('onBeforeMount');
    });

    onMounted(function() {
      console.log('onMounted');
    });
    onBeforeUpdate(function() {
      console.log('onBeforeUpdate');
    });
    onUpdated(function() {
      console.log('onUpdated');
    });
    onBeforeUnmount(function() {
      console.log('onBeforeUmnout');
    });
    onUnmounted(function() {
      console.log('onUnmounted');
    });

    return { userName, age };
  }
  //   computed: {
  //     userName() {
  //       return this.firstName + ' ' + this.lastName;
  //     }
  //   }
};
</script>
