<template>
    <div>
      <h3 v-for="name in fullNames" :key="name.firstname"> 
      <slot :firstname="name.firstname" :lastname="name.lastname"></slot>
      </h3>
    </div>
</template>

<script>
    export default {
        name:'Namelist',
        data() {
            return {
                fullNames:[
                    {     
                     firstname: 'ronaldo',
                     lastname: 'cristiano'
                    },
                    {
                     firstname: 'ramos',
                     lastname: 'sergio'
                    },
                    {
                     firstname: 'benzema',
                     lastname: 'karims'
                    }
                ],
            }
        }
    }
</script>

<style scoped>

</style>