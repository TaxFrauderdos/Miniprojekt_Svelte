<script>
    import Keyboard from "./Keyboard.svelte";
    let display = "";
    let memory = 0;
    let arithmetic = null;
    function updateDisplay(e) {
        let val = e.target.value;
        if (Number(val) >= 0) {
            display += val;
        } else {
            switch (val) {
                case "AC":
                    display = "";
                    memory = 0;
                    break;
                case "C":
                    display = display.slice(0, -1);
                    break;
                case "+":
                    SetOperator("+");
                    break;
                case "-":
                    SetOperator("-");
                    break;
                case "*":
                    SetOperator("*");
                    break;
                case "/":
                    SetOperator("/");
                    break;
                case ",":
                    if(display.includes(".")){
                        return;
                    }
                    display += ".";
                    break;
                case "=":
                    calculate();
                    break;
                default:
                    break;
            }
        }
    }
    function SetOperator(operator){
        if(arithmetic){
            calculate;
        }
        else{
            memory = parseFloat(display);
        }
        arithmetic = operator;
        display = "";

    }
    function calculate(){
        if(!arithmetic){
            return;
        }
        let value = parseFloat(display);
        switch(arithmetic){
            case "+":
                memory += value;
                break;
            case "-":
                memory -= value;
                break;
            case "*":
                memory *= value;
                break;
            case "/":
                memory /= value;
                break;
        }
        display = memory;
        arithmetic = null;
    }
</script>

<fieldset>
    <input type="text" value={display} disabled />
    <Keyboard on:click={updateDisplay} />
</fieldset>

<style>
    input {
        width: 100%;
        height: 10rem;
        font-size: 3.5rem;
        background-color: black;
        color: green;
        text-align: right;
        margin-top: 10px;
        margin-bottom: 10px;
        padding: 10px 4px 10px 4px;
        font-family: lcd;
        border: 1px solid yellow;
        border-radius: 4px;
    }
</style>
