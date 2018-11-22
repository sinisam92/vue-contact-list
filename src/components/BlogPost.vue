<template>
<div>
     <h3>{{ title }}</h3>
    <button @click="functionInChild">Hello</button> <br>
    {{ message }}
    <br>
    {{getReversedMessageMethod()}}
    <br>
    {{reverseMessageComputed}}
</div>
   
</template>

<script>
export default {
    data() {
        return {
            message: 'Ovo je neka poruka'
        }
    },
   props: ['title'],
   methods: {
       functionInChild() {
           this.$emit('callParentFunction', 'Jack', 29)
           
       },
       getReversedMessageMethod() {
           return this.message.split(' ').reverse().join(' ')
       }
   },
   computed: {
       reverseMessageComputed() {
            return this.message.split(' ').reverse().join(' ')
       }
   }
}
</script>

