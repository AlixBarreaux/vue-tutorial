<template>
    <div>
        <p v-text="dropdownResult"></p>
        <DropdownTest @update:option="optionUpdate" />
    </div>
</template>

<script>
    import DropdownTest from "./DropdownTest.vue"

    export default {
        name: "ListComp",

        data() {
            return {
                dropdownResult: ""
            }
        },

        components: {
            DropdownTest
        },

        methods: {
            optionUpdate(value) {
                console.log(value);
                this.dropdownResult = value;
            }
        }
    }
</script>