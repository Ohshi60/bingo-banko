<!-- <h1 class="text-3xl font-bold underline text-red">
  Hello world!
</h1>
 -->
<script>
  // create array with 1-90
  let numbers = Array.from(Array(91).keys()).slice(1)

  let pickedNumbers = []

  function clickedNumber(num) {
    // console.log('los eventos', event.target.innerHTML)
    console.log('received number', num)
    pickedNumbers.push(num)
    pickedNumbers = pickedNumbers
    console.log('hisory', pickedNumbers)
  }   
</script>

<div class="flex">
  <div class="flex flex-row flex-wrap space-between w-1/2" >
    {#each numbers as number}
      <!-- {#if pickedNumbers.includes(number)}
      {/if} -->
      <p on:click={() => clickedNumber(number)} class="px-4 {pickedNumbers.includes(number) ? 'bg-red-200' : ''}">{number}</p>
      
    {/each}
  </div>
  <div class="flex items-center justify-center h-screen w-1/2">
    <p class="text-5xl">{pickedNumbers[pickedNumbers.length-1]}</p>
  </div>
</div>





<style lang="postcss">
  :global(html) {
    background-color: theme(colors.gray.200);
  }
</style>