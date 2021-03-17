<template>
  <section>
    <amount></amount>
  </section>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ user.age }}</h3>
    <button @click="setAge">Change Age</button><br />
    <br />
    <div>
      <input
        type="text"
        placeholder="First Name"
        v-model="firstName"
      /><br /><br />
      <input type="text" placeholder="Last Name" v-model="lastName" />
      <!--@input="setLastName" @input="setFirstName"-->
    </div>
  </section>
  <section>
    <goals></goals>
  </section>
</template>

<script>
import { reactive, ref, computed } from 'vue';
import Goals from './components/goals.vue';
import Amount from './components/amount.vue';
//import { ref } from 'vue';
export default {
  components: { Goals, Amount },
  setup() {
    // const uName = ref('Dhara');
    // const uAge = ref(23);
    /* const user = ref({
       name: 'Dhara',
       age: 23
    }); */
    const firstName = ref('');
    const lastName = ref('');
    const user = reactive({
      age: 23,
    });
    // name: 'Dhara',

    /* watch(age, function(newValue, oldValue) {
      console.log('Old Age: ' + oldValue );
      console.log('New Age: '+ newValue)
    });*/
    const userName = computed(function () {
      return firstName.value + ' ' + lastName.value;
    });

    function setNewAge() {
      user.age = this.user.age + 1;
    }

    /* function setFirstName(event) {
      firstName.value = event.target.value;
    }

    function setLastName(event) {
      lastName.value = event.target.value;
    }
     setTimeout(function() {
      // uName.value = 'Mann';
      // uAge.value = 19;
      user.name = 'Mann';
      user.age = 19;
    }, 2000);*/

    // const userRefs = toRefs(user);
    // return { user: user, userName: userRefs.name, userAge: userRefs.age };

    return {
      /* userName: user.value.name, age: user.value.age,*/ user: user,
      userName: userName,
      setAge: setNewAge,
      firstName,
      lastName,
    };
  },
  //  data() {
  //  return {
  //  userName: 'Maximilian',
  // };
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
