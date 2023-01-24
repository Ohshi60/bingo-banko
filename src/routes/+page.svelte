<!-- <h1 class="text-3xl font-bold underline text-red">
  Hello world!
</h1>
 -->
<script>
	// create array with 1-90
	let numbers = Array.from(Array(91).keys()).slice(1);

	let pickedNumbers = [];

	function clickedNumber(num) {
		// console.log('los eventos', event.target.innerHTML)
		console.log('received number', num);
		pickedNumbers = pickedNumbers.includes(num)
			? pickedNumbers.filter((n) => n !== num)
			: [...pickedNumbers, num];

		console.log('hisory', pickedNumbers);
	}
</script>

<div class="flex">
	<div class="flex flex-row flex-wrap space-between w-1/2">
		{#each numbers as number}
			<!-- {#if pickedNumbers.includes(number)}
      {/if} -->
			<p
				on:click={() => clickedNumber(number)}
				class="px-4 {pickedNumbers.includes(number) ? 'bg-red-200' : ''}"
			>
				{number}
			</p>
		{/each}
	</div>
	<div class="flex flex-col items-center justify-center h-screen w-1/2">
		<p class="text-9xl">{pickedNumbers.length ? pickedNumbers[pickedNumbers.length - 1]: 'Start'}</p>
		<p class="text-base text-blue-600 pt-10">{pickedNumbers}</p>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.200);
	}
</style>
