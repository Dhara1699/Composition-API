<template>
    <section>
        <h2>{{ userName }}</h2>
    </section>
</template>

<script>
import { computed } from 'vue';
export default {
    props: ['firstName' , 'lastName'],

    setup(props) {
        const uName = computed(() => {
            return props.firstName + ' ' + props.lastName;
        });

        return { userName: uName };
    }

   /* computed: {
        userName() {
            return this.firstName + ' ' + this.lastName;
        }
    }*/
}
</script>
