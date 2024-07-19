<script>
  import PercentIcon from "$lib/Icons/percenticon.svelte";
  import Squarerooticon from "$lib/Icons/Square root icon.svelte";
  import Subtractionicon from "$lib/Icons/subtraction icon.svelte";
  import Divisionicon from "$lib/Icons/division icon.svelte";
  import Multiplicationicon from "$lib/Icons/multiplication icon.svelte";
  import Equalityicon from "$lib/Icons/equality icon.svelte";
  import Additionicon from "$lib/Icons/addition icon.svelte";
</script>


<svelte:head>
  <title>
    آلة حاسبة
  </title>
</svelte:head>


  <div class="bg-white h-fit w-fit rounded-3xl grid grid-cols-4 gap-3 p-6 pt-7 font-semibold shadow-xl text-3xl">
   <div class="bg-violet-500 rounded-full col-span-4 h-20 flex items-center px-6 mb-2 text-white shadow-xl"> 123456</div>
    <button class="bg-violet-200 ">
      <!-- %-->
      <PercentIcon/>
    </button>
    <button class=" bg-violet-200">
      <!-- Square root icon-->
      <Squarerooticon/>
    </button>
    <button class="bg-violet-200">CE</button>
    <button class="text-white bg-violet-500 border-0">C</button>
    <button>7</button>
    <button>8</button>
    <button>9</button>
    <button class="text-white bg-violet-600 border-0">
      <!-- subtraction icon-->
      <Subtractionicon/>
    </button>
    <button>4</button>
    <button>5</button>
    <button>6</button>
    <button class="text-white bg-violet-700">
      <!--division icon -->
      <Divisionicon/>
    </button>
    <button>1</button>
    <button>2</button>
    <button>3</button>
    <button class="text-white bg-violet-800">
      <!-- multiplication icon -->
      <Multiplicationicon/>
    </button>
    <button class="text-4xl">.</button>
    <button>0</button>
    <button class="bg-violet-200 ">
      <!-- equality icon -->
       <Equalityicon/>
    </button>
    <button class="text-white bg-violet-900 ">
      <!-- addition icon-->
      <Additionicon/>
    </button>
    
  </div> 

