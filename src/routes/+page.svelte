<script>

import Headling from "$lib/Headling.svelte";

    let text = $state("❤️")
    let pressed = true
   

    function changeText(){
        if (pressed = true) {
            text = "💔"
            pressed = false
        } 
        if (pressed = false) {
            text = "❤️"
            pressed = true
        }
    }

    let pocet = $state(0)
    function pocitadlo(){
        pocet +=1
    }


 

</script>

<div class="headings">
    <Headling zprava = "Svelte"/>
    <Headling zprava = "je"/>
    <Headling zprava = "brnkačka"/>
</div>

<div class="container">
    <p>{pocet}</p> 
    <div class="buttons">
        <button onclick={pocitadlo}>click for bigger score</button>
        <button onclick={changeText}>{text}</button>
    </div>
</div>







<style>

* {
    font-family: monospace;
}

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    gap: 10px;
}

.container > p {
    font-size: 2em;
}

.buttons > button{
    border: 1px solid black;
    border-radius: 50000px;
    padding: 10px 20px;
    background-color: lightblue;
    font-size: 1.5em;
}

.buttons > button:nth-of-type(1) {
    background-color: lightblue;
}

.buttons > button:nth-of-type(2) {
    background-color: rgb(228, 191, 191);
}

.headings {
    position: absolute;
}

:global(.headings > h2) {
	position: absolute;
    font-size: 3em;

}

:global(.headings > h2:nth-child(1)) {
	left: 300px;
	top: 50px;
}

:global(.headings > h2:nth-child(2)) {
	left: 200px;
	top: 200px;
}

:global(.headings > h2:nth-child(3)) {
	left: 300px;
	top: 350px;
}


</style>