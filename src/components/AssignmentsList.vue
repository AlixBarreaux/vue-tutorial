<template>
    <section v-show="assignments.length">
            <h2 class="font-bold mb-2">{{ title }}</h2>
            <ul>
               <assignment 
                    v-for="assignment in assignments"
                    :key="assignment.id" 
                    :assignment="assignment"
                ></assignment>
            </ul>
        </section> 
</template>

<script>
    import Assignment from "./AssignmentComp.vue";

    export default {
        components: {
            Assignment
        },

        props: {
            assignments: Array,
            title: String
        }
    }
</script>
