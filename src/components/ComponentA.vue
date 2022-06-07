<template>
   <div>
       <h2>ComponentA</h2>
       <ComponentB />
   </div>
</template>


<script>
import ComponentB from './ComponentB'

export default {
    name: 'ComponentA',
    components: {
        ComponentB,
    },
}
</script>

<style>

</style>