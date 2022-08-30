<template>
    <div class="logo"><b><span>M</span><span>O</span><span>R</span>PI<span>O</span><span>N</span></b></div>
    <ul class="game">
        <li class="empty" id="case1" @click="clickOnCell($event, 1)"></li>
        <li class="empty" id="case2" @click="clickOnCell($event, 2)"></li>
        <li class="empty" id="case3" @click="clickOnCell($event, 3)"></li>
        <li class="empty" id="case4" @click="clickOnCell($event, 4)"></li>
        <li class="empty" id="case5" @click="clickOnCell($event, 5)"></li>
        <li class="empty" id="case6" @click="clickOnCell($event, 6)"></li>
        <li class="empty" id="case7" @click="clickOnCell($event, 7)"></li>
        <li class="empty" id="case8" @click="clickOnCell($event, 8)"></li>
        <li class="empty" id="case9" @click="clickOnCell($event, 9)"></li>
    </ul>
    <footer>
        <input id="reset" type="button" onclick='window.location.reload()' value="🏁Relancer la partie🏁" />
    </footer>
</template>

    
<script>
export default {
    name: 'startGame',
    data() {
        return {
            playersPosition: [[], []],
            turn: 0
        }
    },


    methods: {

        clickOnCell(event, numberCell) {
            this.playersPosition[this.turn].push(numberCell)
            console.log(this.playersPosition)
            if (event.target.className == "empty") {
                if (this.turn == 0) {
                    event.target.classList.add("circle")
                    event.target.classList.remove("empty")

                    if (this.playersPosition[this.turn].length == 3) {
                        let temp = this.playersPosition[this.turn].join('')
                        this.boardWinner(temp)
                    }
                    this.turn = 1
                } else {
                    event.target.className = "cross"

                    if (this.playersPosition[this.turn].length == 3) {
                        let temp = this.playersPosition[this.turn].join('')
                        this.boardWinner(temp)
                    }
                    this.turn = 0
                }
            }

        },
        boardWinner(temp) {
            let numberWin =
                [123, 456, 789, 147, 258, 369, 159, 357]
            let victory = numberWin.findIndex(element => element == temp)
            return victory
        },
    },
}

</script>
    <style scoped>
    ul {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-gap: 1px;
        padding: 0.3em;
    }
    
    ul.game {
        width: 319px;
        height: 319px;
        margin: 0 auto;
    }
    
    ul.game li {
        margin: 0;
        padding: 0;
        list-style: none;
        background: whitesmoke;
        display: inline-block;
        cursor: grab;
        border: 2px solid rgb(255, 148, 210);
    }
    
    ul.game li.circle {
        background-image: url(https://pluspng.com/img-png/letter-o-png-letter-o-icon-112643-512.png);
        background-size: 100% 130%;
        background-position: center;
    
    }
    
    ul.game li.cross {
        background-position: center;
        background-size: 100% 150%;
        background-image: url(https://freepngimg.com/download/alphabets/22-2-x-alphabet-png.png)
    }
    
    #reset {
        display: inline-block;
        background-color: #7b38d8;
        border-radius: 10px;
        border: 4px double #cccccc;
        color: #eeeeee;
        text-align: center;
        font-size: 15px;
        padding: 10px;
        width: 200px;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
        -o-transition: all 0.5s;
        transition: all 0.5s;
        cursor: pointer;
        margin: 5px;
    }
    
    #reset:hover {
        background-color: green;
    }
    </style>