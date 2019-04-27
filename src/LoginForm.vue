<template>
   <div>
       <label>{{ header }}</label>
       <input type="email" v-model="email">
       <button @click="enter()">{{buttonLabel}}</button>
   </div>
</template>

<script>
export default {
    props: ['buttonLabel', 'header'],  //Pole pozwala zdefiniwować u rodzica wartość
    data() {
        return {
            //  Stan komponentu
            email: ''
        }
    },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 }
}
</script>