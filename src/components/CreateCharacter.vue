<template>
    <div>
        <!-- Cheat sheet:
        Single arg:
        <CharacterForm @formValidated="displayCharacterInfo">
            
        Several args:
        <CharacterForm @formValidated="(args) => displayCharacterInfo(args)">
        -->
        <CharacterForm @formValidated="displayCharacterInfo">
            <template #default="defaultSlotProps"><p><strong>Brand: {{ defaultSlotProps.brand }} Amount: {{ defaultSlotProps.amount }}</strong></p></template>
            <template #main-content="mainContentSlotProps"><p><em>Changed main content: {{ mainContentSlotProps.mainText }}</em></p></template>
            <template #ending-content><h4>Changed ending content</h4></template>
        </CharacterForm>
        
    </div>
</template>^

<script>
    import CharacterForm from './CharacterForm.vue';

    export default {
        name: "CreateCharacter",

        data() {
            return  {
                title: ""
            }
        },

        components: {
            CharacterForm
        },

        methods: {
            displayCharacterInfo() {
                console.log("Signal received!");
                alert("Title updated! FINALLY! :)");
            }
        }
    }
</script>

<!-- DISPLAY RECAP AND HIDE FORM ONCE SUBMITED -->
<!-- ENTER PLAYER ID AS PROP TO TEST PASSING VALUE TO CHILD -->
<!-- CharacterForm PREVENT DEFAULT -->