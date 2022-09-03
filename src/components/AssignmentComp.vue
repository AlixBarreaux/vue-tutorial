<template>
    <li>
        <label>
            {{ assignment.name }}
            <input type="checkbox" v-model="assignment.complete">
        </label>
    </li> 
</template>

<script>
    export default {
        name: "AssignmentComp",
        props: {
            assignment: Object
        }
        }
</script>


