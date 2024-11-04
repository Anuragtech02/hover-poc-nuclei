<script lang="ts">
	const COMMON_CLASSES = 'relative sm:h-full cursor-pointer rounded-md';
</script>

<section class="bg-grey-100 flex h-screen w-screen items-center justify-center">
	<div class="container mx-auto">
		<div class="row-1 flex flex-nowrap items-stretch justify-between gap-4">
			{#each Array.from({ length: 4 }, (_, i) => i) as i}
				<div class="{COMMON_CLASSES} card-1">
					<div
						class="front absolute left-0 top-0 z-[1] flex h-full w-full items-end justify-start rounded-md bg-cover p-6 font-bold text-white"
						style="background-image: url(/hotel-img.jpg)"
					>
						<span class="z-10 block"> This is a nice title</span>
					</div>
					<div class="content absolute top-0 h-full w-full p-6">
						<ul>
							<li class="pl-4">This is a cool title</li>
							<li class="pl-4">This is a cool title</li>
							<li class="pl-4">This is a cool title</li>
						</ul>
					</div>
				</div>
			{/each}
		</div>
		<div class="row-2 mt-4 flex flex-nowrap items-stretch justify-between gap-4">
			{#each Array.from({ length: 4 }, (_, i) => i) as i}
				<div class="{COMMON_CLASSES} card-2">
					<div
						class="front absolute left-0 top-0 z-[1] flex h-full w-full items-end justify-start rounded-md bg-cover p-6 font-bold text-white"
						style="background-image: url(/hotel-img.jpg)"
					>
						<span class="z-10 block"> This is a nice title</span>
					</div>
					<div class="content absolute top-0 h-full w-full p-6">
						<ul>
							<li class="pl-4">This is a cool title</li>
							<li class="pl-4">This is a cool title</li>
							<li class="pl-4">This is a cool title</li>
						</ul>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<style lang="postcss">
	:root {
		--h-row1: 350px;
		--h-row2: 350px;

		--content-transition: all 0.5s cubic-bezier(0.19, 1, 0.22, 1);
		--front-transition: all 0.5s cubic-bezier(0.19, 1, 0.22, 1);
		--row-height-transition: all 0.8s cubic-bezier(0.19, 1, 0.22, 1);
	}

	.card-1,
	.card-2 {
		@apply w-full;
		transition: all 0.5s cubic-bezier(0.19, 1, 0.22, 1);
	}

	.content {
		left: 0;
		z-index: -1;
	}

	.card-1 .front::before,
	.card-2 .front::before {
		@apply absolute inset-0 rounded-md;
		content: '';
		background: linear-gradient(to top, rgba(0, 0, 0, 0.548), transparent);
	}

	.row-1 {
		height: var(--h-row1);
		transition: var(--row-height-transition);
	}

	.row-2 {
		height: var(--h-row2);
		transition: var(--row-height-transition);
	}

	.row-1:hover {
		--h-row1: 400px;
		--h-row2: 150px;
	}

	.row-2:hover {
		--h-row1: 150px;
		--h-row2: 400px;
	}
	.card-1:hover {
		width: 160%;
	}

	.card-1:hover .front {
		width: 50%;
		transition: var(--front-transition);
	}

	.card-1:hover .content {
		width: 50%;
		left: auto;
		right: 0;
		transition: var(--content-transition);
	}

	.card-1:hover ~ .card-1 {
		width: 80%;
	}

	.card-2:hover {
		width: 160%;
	}

	.card-2:hover .front {
		width: 50%;
		transition: var(--front-transition);
	}

	.card-2:hover .content {
		width: 50%;
		left: auto;
		right: 0;
		transition: var(--content-transition);
	}

	.card-2:hover ~ .card-2 {
		width: 80%;
	}
</style>
