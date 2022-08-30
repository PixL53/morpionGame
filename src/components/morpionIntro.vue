<template>
  <div class="logo"><b><span>M</span><span>O</span><span>R</span>P<span>I</span><span>O</span><span>N</span></b></div>
  <div>
    <h2>Règle du jeu</h2>
    <ul>
      <li>
        <p>Jeu qui se joue à deux joueurs, sur un damier de 3 cases par 3 cases.</p>
      </li>
      <li>
        <p>Chaque joueur est représenté par un "symbole".</p>
      </li>
      <li>
        <p>Un joueur utilise toujours le même type de "symbole".</p>
      </li>
      <li>
        <p>Un premier joueur dessine son symbole sur une case. Puis c'est au tour de l'autre joueur de dessiner son
          symbole sur une case vide.</p>
      </li>
      <li>
        <p>Le but du jeu est de réussir à aligner ses trois symboles (horizontal, vertical ou diagonale), on remporte
          alors la partie.</p>
      </li>
      <li>
        <p>Si la grille est remplie et qu'aucune ligne ne comporte trois symboles identiques, les joueurs finissent par
          un match nul.</p>
      </li>
    </ul>
  </div>
  <footer>
    <input type="button" value="🎮C'EST PARTI🎮" @click="nextStep">
  </footer>
</template>

<script>
export default {
  name: 'MorpionIntro',
  methods: {
    nextStep() {
      this.$emit("nextStep")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#btn-twtr:hover {
  color: #fff;
  opacity: 1
}

h2 {
  text-decoration: underline;
}

h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: "👾";
  width: 45vw;
  margin: 0 auto;
}

li {
  margin: 0 10px;

}

p {
  font-size: em;
  color: #ffffff;
}

input {
  display: inline-block;
  background-color: #7b38d8;
  border-radius: 10px;
  border: 4px double #cccccc;
  color: #eeeeee;
  text-align: center;
  font-size: 15px;
  padding: 10px;
  width: 160px;
  -webkit-transition: all 0.5s;
  -moz-transition: all 0.5s;
  -o-transition: all 0.5s;
  transition: all 0.5s;
  cursor: pointer;
  margin: 5px;
}

input:hover {
  background-color: green;
}
</style>
