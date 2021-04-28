<script>
	export let images;
	export let title;

	$: activeImage = 0;

	function changeImg(e) {
		let i = images.length;
		if (e == 1) {
			if (activeImage == 0) activeImage = i - 1;
			else activeImage -= 1;
		} else {
			if (i == activeImage + 1) activeImage = 0;
			else activeImage += 1;
		}
	}
</script>

<img class="bgw" src={images[activeImage]} alt={title}/>
<button class="arrow arrowLeft" on:click={() => changeImg(1)}>&lsaquo;</button>
<button class="arrow arrowRight" on:click={() => changeImg(2)}>&rsaquo;</button>

<style>
	.arrow {
		background-color: transparent;
		color: #fff;
		position: absolute;
		top: 0;
		width: 70px;
		height: 100%;
		font-size: 7rem
	}

	.arrowLeft { left: 0 }

	.arrowRight { right: 0 }

	button { cursor: pointer }

	.rel {
		position: relative
	}

	.bgw {
		background-color: #fff
	}
</style>
