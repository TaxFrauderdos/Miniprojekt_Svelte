<section id = 'keyBoard'>
    <button class = "b7" on:click >7</button>
    <button class = "b8" on:click >8</button>
    <button class = "b9" on:click >9</button>
    <button class = "add" on:click >+</button>

    <button class = "b4" on:click >4</button>
    <button class = "b5" on:click >5</button>
    <button class = "b6" on:click >6</button>
    <button class = "sub" on:click >-</button>

    <button class = "b1" on:click >1</button>
    <button class = "b2" on:click >2</button>
    <button class = "b3" on:click >3</button>
    <button class = "mul" on:click >*</button>
    
    <button class = "comma" on:click >,</button>
    <button class = "b0" on:click >0</button>
    <button class = "enter" on:click >=</button>
    <button class = "div" on:click >/</button>

    <button id='clear' style = 'grid-column: span 4;'>CLEAR</button>
</section>

<style>
    section{
        display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: minmax(10rem, auto);
    grid-gap: 0.1rem;
    grid-column: span 4;
    padding: 0.2rem;
    }
    button{
        border: 1px solid gray;
        border-radius: 4px;
        font-size: 4rem;
        &:hover{
            background-color: lightgray;
        }
        &.add, &.sub, &.mul, &.div, &.comma, &.enter, &.clear{
            color: cyan;
        }
    }
</style>