<template>
    <form @submit.prevent="add()">
        <input v-model="newAssignment" type="text" placeholder="New assignment..." />
        <button type="submit">Add</button>
    </form>
</template>

<script>
export default {
    name: 'AssignmentCreate',
    components: {
        
    },

    data() {
        return {
            newAssignment: ""
        }
    },

    methods: {
        add() {
            alert(this.newAssignment);
            this.newAssignment = "";
        }
    }
    }
</script>