<script lang="ts">
  import PercentIcon from "$lib/Icons/percenticon.svelte";
  import Squarerooticon from "$lib/Icons/Square root icon.svelte";
  import Subtractionicon from "$lib/Icons/subtraction icon.svelte";
  import Divisionicon from "$lib/Icons/division icon.svelte";
  import Multiplicationicon from "$lib/Icons/multiplication icon.svelte";
  import Equalityicon from "$lib/Icons/equality icon.svelte";
  import Additionicon from "$lib/Icons/addition icon.svelte";
  let equation: string= "";

  function addToEquation(value: string) {
    equation+=value;
  }

  function clear(){
  equation = " ";
  }
  function backspace(){
    equation = equation.substring(0,equation.length-1).trim().trimStart();
    
  
}
</script>




<svelte:head>
  <title>
    آلة حاسبة
  </title>
</svelte:head>

<!--TODO: fix overflowing numbers-->
  <div class="bg-white h-fit w-fit rounded-3xl grid grid-cols-4 gap-3 p-6 pt-7 font-semibold shadow-xl text-3xl"> 
   <div class="bg-violet-500 rounded-full col-span-4 h-20 flex items-center px-6 mb-2 text-white shadow-xl"> {equation}</div>
    <button on:click={()=>addToEquation(' / 100')} class="bg-violet-200 ">
      <!-- %-->
      <PercentIcon/>
    </button>
  
    <button on:click={backspace} class="bg-violet-200">CE</button>
    <button on:click={clear} class=" bg-violet-200">C</button>
     <button on:click={()=>addToEquation(' - ')} class="text-white bg-violet-500">
      <!-- subtraction icon-->
      <Subtractionicon/>
    </button>
    <button on:click={()=>addToEquation('7')}>7</button>
    <button on:click={()=>addToEquation('8')}>8</button>
     <button on:click={()=>addToEquation('9')}>9</button>
     <button on:click={()=>addToEquation(' / ')} class="text-white bg-violet-600">
      <!--division icon -->
      <Divisionicon/>
    </button>
    <button on:click={()=>addToEquation('4')}>4</button>
    <button on:click={()=>addToEquation('5')}>5</button>
    <button on:click={()=>addToEquation('6')}>6</button>
        <button on:click={()=>addToEquation(' * ')} class="text-white bg-violet-700">
      <!-- multiplication icon -->
      <Multiplicationicon/>
    </button>
    <button on:click={()=>addToEquation('1')} >1</button>
    <button on:click={()=>addToEquation('2')}>2</button>
    <button on:click={()=>addToEquation('3')} >3</button>
    <button on:click={()=>addToEquation(' + ')} class="text-white bg-violet-800 ">
      <!-- addition icon-->
      <Additionicon/>
    </button>
    <button on:click={()=>addToEquation('.')} class="text-4xl">.</button>
    <button on:click={()=> addToEquation('0')} class="col-span-2 w-full flex items-center px-6 mb-2">0</button>
    <button on:click={()=>addToEquation(' = ')} class="bg-violet-900 text-white">
      <!-- equality icon -->
       <Equalityicon/>
    </button>

  </div> 

