<script lang="ts">
  import PercentIcon from "$lib/Icons/percenticon.svelte";
  import Subtractionicon from "$lib/Icons/subtraction icon.svelte";
  import Divisionicon from "$lib/Icons/division icon.svelte";
  import Multiplicationicon from "$lib/Icons/multiplication icon.svelte";
  import Equalityicon from "$lib/Icons/equality icon.svelte";
  import Additionicon from "$lib/Icons/addition icon.svelte";
  import { onMount } from "svelte";
  let equation: string = "";

  function addToEquation(value: string) {
    equation += value;
    setTimeout(() => {
      //@ts-ignore
      document.activeElement?.blur();
    }, 600);
  }

  function clear() {
    equation = " ";
  }
  function backspace() {
    // equation = equation.substring(0,equation.length-1).trim();
    switch (equation.substring(equation.length - 3, equation.length)) {
      case " + ":
      case " * ":
      case " - ":
      case " / ":
        equation = equation.substring(0, equation.length - 3);
        break;
      default:
        equation = equation.substring(0, equation.length - 1);
        setTimeout(() => {
          //@ts-ignore
          document.activeElement?.blur();
        }, 600);
    }
  }

  function solve() {
    try {
      let answer = eval(equation);
      if (answer == undefined || answer == Infinity ) throw SyntaxError;
      equation = answer;
    } catch (error) {
      let output = document.getElementById("output");
      output?.classList.add("!bg-red-500");
      setTimeout(() => {
        output?.classList.remove("!bg-red-500");
      }, 600);
      setTimeout(() => {
      //@ts-ignore
      document.activeElement?.blur();
    }, 600);
    }
  }

  function onKeyDown(e: KeyboardEvent) {
    let button = document.getElementById(e.key);
    button?.click();
    button?.focus();
    setTimeout(() => {
      //@ts-ignore
      document.activeElement?.blur();
    }, 600);
  }

  onMount(() => {
    let allButtuns = document.getElementsByTagName("button");
    for (let i = 0; i < allButtuns.length; i++) {
      allButtuns[i].addEventListener("click", () => {
        new Audio("/click.wav").play();
      });
    }
  });
</script>

<svelte:head>
  <title>آلة حاسبة</title>
</svelte:head>

<svelte:window on:keydown|preventDefault={onKeyDown} />
<div
  class="bg-white rounded-3xl grid grid-cols-4 gap-3 p-6 pt-7 font-semibold shadow-xl text-3xl max-w-[25rem] max-h-fit"
>
  <!--Output-->
  <div
    id="output"
    class="bg-violet-500 rounded-3xl col-span-4 min-h-20 flex items-center px-6 mb-2 text-white shadow-xl break-all transition-all"
  >
    {equation}
  </div>

  <button id="Delete" on:click={clear} class=" bg-violet-200">C</button>
  <button id="Backspace" on:click={backspace} class="bg-violet-200">Del</button>
  <button
    id="%"
    on:click={() => addToEquation(" / 100")}
    class="bg-violet-400 text-white"
  >
    <!-- %-->
    <PercentIcon />
  </button>
  <button
    id="-"
    on:click={() => addToEquation(" - ")}
    class="text-white bg-violet-500"
  >
    <!-- subtraction icon-->
    <Subtractionicon />
  </button>
  <button id="7" on:click={() => addToEquation("7")}>7</button>
  <button on:click={() => addToEquation("8")}>8</button>
  <button on:click={() => addToEquation("9")}>9</button>
  <button
    id="/"
    on:click={() => addToEquation(" / ")}
    class="text-white bg-violet-600"
  >
    <!--division icon -->
    <Divisionicon />
  </button>
  <button id="4" on:click={() => addToEquation("4")}>4</button>
  <button id="5" on:click={() => addToEquation("5")}>5</button>
  <button id="6" on:click={() => addToEquation("6")}>6</button>
  <button
    id="*"
    on:click={() => addToEquation(" * ")}
    class="text-white bg-violet-700"
  >
    <!-- multiplication icon -->
    <Multiplicationicon />
  </button>
  <button id="1" on:click={() => addToEquation("1")}>1</button>
  <button id="2" on:click={() => addToEquation("2")}>2</button>
  <button id="3" on:click={() => addToEquation("3")}>3</button>
  <button
    id="+"
    on:click={() => addToEquation(" + ")}
    class="text-white bg-violet-800"
  >
    <!-- addition icon-->
    <Additionicon />
  </button>
  <button id="." on:click={() => addToEquation(".")} class="text-4xl">.</button>
  <button
    id="0"
    on:click={() => addToEquation("0")}
    class="col-span-2 w-full flex items-center px-6 mb-2">0</button
  >
  <button id='=' on:click={() => solve()} class="bg-violet-900 text-white">
    <!-- equality icon -->
    <Equalityicon />
  </button>
</div>
