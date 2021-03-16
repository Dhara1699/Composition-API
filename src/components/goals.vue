<template>
  <section class="container">
    <h2>My Course Goal</h2>
    <h3 v-if="courseData.goalIsVisible">{{ goal }}</h3>
    <button @click="toggleGoalVisibility">Toggle Goal</button>
  </section>
</template>

<script>
import { reactive } from 'vue';
export default {
  setup() {
   // const courseGoal = ref('Finish the Goal!');

   // const goalIsVisible = ref(false);

   //const courseData = ref({
   //    goal: 'Finish The Course!',
   //    goalIsVisible: false
   //});

   const courseData = reactive({
       goal: 'Finish The Course!',
       goalIsVisible: false
   });

    function toggleGoalVisibility() {
     // goalIsVisible.value = !goalIsVisible.value
     //courseData.value.goalIsVisible = !courseData.value.goalIsVisible;
     courseData.goalIsVisible = !courseData.goalIsVisible;
    }

    return { goal: courseData.goal, courseData, toggleGoalVisibility };
  },
};
</script>


<style scoped>
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