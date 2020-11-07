<template>
    <div>
      <button @click="onReturn">Back</button>

      Excercise 2
      <Example />
    </div>
</template>

<script>
import Example from './Example';

export default {
    props: ['onReturn'],
    components: {
      Example
    }
};
</script>

<style>
</style>