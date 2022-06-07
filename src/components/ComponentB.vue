<template>
   <div>
       <h2>ComponentB</h2>
       <ComponentC />
   </div>
</template>


<script>
import ComponentC from './ComponentC'

export default {
    name: 'ComponentA',
    components: { 
        ComponentC,
    },
}
</script>

<style>

</style>