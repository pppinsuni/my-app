<script>
  let total=0;
  let console="";
  let state = null;
  function resolveState(){
    switch(state){
      case "add":
        total += parseFloat(console);
        console = "0";
        break;
      case "substract":
        total -= parseFloat(console);
        console = "0";
        break;
      case "multiply":
        total *= parseFloat(console);
        console = "0";
        break;
      case "add":
        total /= parseFloat(console);
        console = "0";
        break;
      default :
        total = parseFloat(console);
        console = "0";
        break;
    }
  }
  function setOperation(operation){
    resolveState();
    state=operation;
  }
  function setValue(value){
    if(console.toString()=="0" || state == "equal")
    console = "";
    if(state == "equal"){
      state = null;
    }
    if(value=="c"){
      total = 0;
      state = null;
      console = "";
      return;
    }
    console = console + value;
  }
  function equal(){
    resolveState();
    console = total;
    state = "equal";
  }
</script>

<!-- <script lang="ts">
import { Button } from "../components/button";

  import { Button } from "@src/components/button";

  const textNumbers : string[] = ['1','2','3','4','5','6','7','8','9','0'];
</script>

<div class ="frame">
  {#each textNumbers as text}
  <Button {text} color="orange" onClick={(value) => alert(value)}/>  
  {/each}
</div> -->

<!-- <style lang="scss">
  .frame{
    width: 240px;
    display: flex;
    flex-wrap: wrap;
  }
</style> -->

<style>
  .calculator {
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    width:300px;
    border:1px solid #eee;
    padding:10px;
  }
  .calculator input{
    width:100%;
    padding:20px;
    outline:none;
    text-align:right;
    font-size:20px;
  }
  .calculator .buttons{
    display:flex;
    flex-wrap:wrap;
  }
  .calculator .buttons .operations {
    display:flex;
    justify-content:space-between;
    width:100%;
  }
  .calculator .buttons .operations button {
    width:24%;
  }
  .calculator .buttons .numbers {
    width:75%;
  }
  .calculator .buttons .numbers>div {
    display:flex;
    justify-content:space-between;
  }
  .calculator .buttons .numbers > div button{
    width:32%;
  }
  .calculator .equal {
    flex:1;
  }
  .calculator .equal button {
    margin-left:5%;
    width:95%;
    height:95%;
    background:#00acee;
    color:#eee;
  }
  .calculator button {
    outline:none;
  }
</style>

<div class = "calculator">
  <input type="text" bind:value={console} readonly="true"/>
  <div class="buttons">
    <div class="operations">
      <button on:click={()=>{setOperation('add');}}>
        +
      </button>
      <button on:click={()=>{setOperation('substract');}}>
        -
      </button>
      <button on:click={()=>{setOperation('multiply');}}>
        &times;
      </button>
      <button on:click={()=>{setOperation('divide');}}>
        &divide;
      </button>
    </div>
    <div class="numbers">
      <div>
        <button on:click={()=>{setValue(7);}}>
          7
        </button>
        <button on:click={()=>{setValue(8);}}>
          8
        </button>
        <button on:click={()=>{setValue(9);}}>
          9
        </button>
      </div>
      <div>
        <button on:click={()=>{setValue(4);}}>
          4
        </button>
        <button on:click={()=>{setValue(5);}}>
          5
        </button>
        <button on:click={()=>{setValue(6);}}>
          6
        </button>
      </div>
      <div>
        <button on:click={()=>{setValue(1);}}>
          1
        </button>
        <button on:click={()=>{setValue(2);}}>
          2
        </button>
        <button on:click={()=>{setValue(3);}}>
          3
        </button>
      </div>
      <div>
        <button on:click={()=>{setValue(0);}}>
          0
        </button>
        <button on:click={()=>{setValue('.');}}>
          .
        </button>
        <button on:click={()=>{setValue(c);}}>
          c
        </button>
      </div>
    </div>
    <div class="equal">
      <button on:click={equal}>
        =
      </button>
    </div>    
  </div>
</div>
