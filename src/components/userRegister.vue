<template>
    <div class="logo"><b><span>M</span><span>O</span><span>R</span>PI<span>O</span><span>N</span></b></div>
    <div id="players">
        <h2>JOUEUR 1</h2>

        <p>Choix du pseudo:
            <input type="text" v-model="item" @keyup.enter="ajouterPseudo">
            <input type="button" value="VALIDER" @click="ajouterPseudo">
        </p>
        <ul>
            <li v-for="(element, index) of Players" v-bind:key="index" @click="ajouterPseudo(index)">
                {{  element  }}
            </li>
        </ul>
        <p>Choix du symbole:
            <select v-model="symbole1">
                <option v-for="(element, index) of symbol" v-bind:key="index" @click="symbole(index)">
                    {{  element  }}</option>
            </select><input type="button" value="VALIDER" @click="symbole">
        </p>


        <h2>JOUEUR 2</h2>

        <p>Choix du pseudo:
            <input type="text" v-model="item2" @keyup.enter="ajouterPseudo">
            <input type="button" value="VALIDER" @click="ajouterPseudo">
        </p>
        <ul>
            <li v-for="(element, index) of Players2" v-bind:key="index" @click="ajouterPseudo(index)">
                {{  element  }}
            </li>
        </ul>
        <p>Choix du symbole:
            <select v-model="symbole2">
                <option v-for="(element, index) of symbol" v-bind:key="index" @click="symbole(index)">
                    {{  element  }}</option>
            </select><input type="button" value="VALIDER" @click="symbole">
        </p>
    </div>
    <footer>
        <input id="boutton" type="button" value="👾COMMENÇONS👾" @click="nextStep">
    </footer>
</template>

<script>

export default {
    name: 'userRegister',
    data() {
        return {
            item: "",
            Players: [],
            symbol: ["⚫", "❌"],
            Players2: [],
        }

    },
    methods: {
        ajouterPseudo() {
            this.Players.push(this.item)
            this.item = ""
            this.Players2.push(this.item2)
            this.item2 = ""
        },
        symbole() {
            this.Players.push(this.symbole1)
            this.symbole1 = ""
            this.Players2.push(this.symbole2)
            this.symbole2 = ""
        },
        nextStep() {
            this.$emit("nextStep")
        }
    },

}
</script>
<style scoped>
#boutton {
    display: inline-block;
    background-color: #7b38d8;
    border-radius: 10px;
    border: 4px double #cccccc;
    color: #eeeeee;
    text-align: center;
    font-size: 15px;
    padding: 10px;
    width: 180px;
    -webkit-transition: all 0.5s;
    -moz-transition: all 0.5s;
    -o-transition: all 0.5s;
    transition: all 0.5s;
    cursor: pointer;
    margin: 5px;
}

li {
    list-style-type: none;
}

#boutton:hover {
    background-color: green;
}

#players {
    padding-bottom: 3em;
}
</style>