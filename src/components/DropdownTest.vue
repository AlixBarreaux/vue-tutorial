<template>
    <select name="dropdown" id="dropdown" v-model="selectedOption" @change="optionChanged">
        <option value="0" disabled>- Please select an option -</option>
        <option value="1">Option 1</option>
        <option value="2">Option 2</option>
        <option value="3">Option 3</option>
    </select>
</template>

<script>
    export default {
        name: "DropdownTest",

        data() {
            return {
                selectedOption: null,
            }
        },

        methods: {
            optionChanged() {
                this.$emit("update:option", this.selectedOption);
            }
        }
    }
</script>