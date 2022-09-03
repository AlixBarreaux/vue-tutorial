<template>
    <div>
        <CharacterForm />
        <!-- @characterFormValidated="displayCharacterInfo()" -->
        <div>
            <p @formValidated="displayCharacterInfo()">Title: {{ this.title }}</p>
        </div>
    </div>
</template>

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

        method: {
            displayCharacterInfo() {
                console.log("Signal received!");
                alert("Title updated! FINALLY! :)");
            },
        }
    }
</script>

<!-- DISPLAY RECAP AND HIDE FORM ONCE SUBMITED -->
<!-- ENTER PLAYER ID AS PROP TO TEST PASSING VALUE TO CHILD -->
<!-- CharacterForm PREVENT DEFAULT -->