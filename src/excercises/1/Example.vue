<template>
    <div>
        <h3>Hello !</h3>
        <div v-if="isChanged">
            <List />
        </div>
        <div :class="{message: true, 'text-danger': isChanged }">{{ message }}</div>
        <button class="btn-success" @click="changeMessage">
            Change message
        </button>
    </div>
</template>

<script>
import List from '../../components/List';

export default {
    components: {
        List
    },
    data() {
        return {
            message: 'Good morning',
            isChanged: false 
        }
    },
    methods: {
        changeMessage() {
           this.message = "Good night!";
           this.isChanged = true;
        }
    }
}
</script>

<style>
    .message {
        color: green;
        font-weight: bold;
    }
</style>