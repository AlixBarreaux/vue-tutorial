<template>
    <form @submit.prevent="validateForm()">
        <label for="race-select">Choose a Race:</label>
        <select name="race-select" id="race-select" v-model="race">
            <option value="human">Human</option>
            <option value="orc">Orc</option>
            <option value="lich">Lich</option>
            <option value="tauren">Tauren</option>
        </select>
        <br /><br />

        <label for="name-input">Enter your name:</label>
        <input name="name-input" type="text" v-model="name" />
        <br /><br />


        <div id="companions-list-input" v-for="companion in 3" :key="companion">
            <label for="">Companion {{ companion }}:</label>
            <input name="" type="text" v-model="companionsList[companion -1]" />
            <br /><br />
        </div>

        

        <button type="submit">Create Character</button>
    </form>
    
    <!--<input type="text" @characterFormValidated="test()" />-->
    <button @click="validateFormAlternate()">Emit signal</button>

    <p>{{ race }}</p>
    <p>{{ name }}</p>
    <p>{{ companionsList }}</p>
</template>

<script>
    export default {
        name: "CharacterForm",

        data() {
            return {
                race: "",
                name: "",
                companionsList: []
            }
        },

        methods: {
            validateForm() {
                console.log("Validating form!");
            },

            validateFormAlternate() {
                console.log("TEST: Validating without filling the form...");
                this.$emit('formValidated');
            },

        },

        created() {
            let pokemon = {};

            fetch("https://pokeapi.co/api/v2/pokemon/squirtle")
            .then(response => response.json())
            .then(data => {
                pokemon = data;
                console.log(data);
                console.log(pokemon);

                this.name = data.name;
                this.race = data.sprites.back_default;
            })
            .catch( (error) => {
                console.error("(!) Error: ", error);
            })
           

            
        }
    }

    
</script>