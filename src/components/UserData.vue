<template>
  <section>
    <h2>{{ userName }}</h2>
  </section>
</template>

<script>
import {
  computed,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from 'vue';
export default {
  props: ['firstName', 'lastName'],

  setup(props) {
    const uName = computed(() => {
      return props.firstName + ' ' + props.lastName;
    });

    onBeforeMount(() => {
      console.log('onBeforeMount');
    });

    onMounted(() => {
      console.log('onMounted');
    });

    onBeforeUpdate(() => {
      console.log('onBeforeUpdate');
    });

    onUpdated(() => {
      console.log('onUpdated');
    });

    onBeforeUnmount(() => {
      console.log('onBeforeUnmount');
    });

    onUnmounted(() => {
      console.log('onUnmounted');
    });

    return { userName: uName };
  },

  /* computed: {
        userName() {
            return this.firstName + ' ' + this.lastName;
        }
    }*/
};
</script>
