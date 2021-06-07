<script>
  // This import is just for reference
	import Game from "./card.svelte";

  // Data comes from here
	export let data;

  // number changes the content
  $: active = 0;

	function changeSlide(e) {
		let i = data.length;
		if (e == 1) {
			if (active == 0) active = i - 1;
			else active -= 1;
		} else {
			if (i == active + 1) active = 0;
			else active += 1;
		}
	}
</script>

{#if data && data.length > 1}
	<div id="slider" class="relative">
		<Game item={data[active]} />

		<div class="grid absolute top-0 left-2 h-full z-20">
			<button
				class="self-center px-3 py-1 font-bold border-none shadow-sm bg-white font-bold text-2xl rounded-md"
				on:click={() => changeSlide(1)}
			>
				&lsaquo;
			</button>
		</div>
		<div class="grid absolute top-0 right-2 h-full z-20">
			<button
				class="self-center px-3 py-1 font-bold border-none shadow-sm bg-white font-bold text-2xl rounded-md"
				on:click={() => changeSlide(2)}
			>
				&rsaquo;
			</button>
		</div>
	</div>
{/if}
