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

<div class="grid grid-cols-2 h-screen">
	<div class="grid grid-cols-10">
		{#each numbers as number}
			<p
				on:click={() => clickedNumber(number)}
				class="px-4 {pickedNumbers.includes(number) ? 'bg-red-200' : ''}"
			>
				{number}
			</p>
		{/each}
	</div>

	<div class="grid place-items-center">
		<p class="text-[256px]">
			{pickedNumbers.length ? pickedNumbers[pickedNumbers.length - 1] : 'Start'}
		</p>
		<p class="text-base text-blue-600 pt-10">{pickedNumbers}</p>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.200);
	}
</style>
