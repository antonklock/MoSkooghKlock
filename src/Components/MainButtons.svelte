<script lang="ts">
	import { Rive } from '@rive-app/canvas';
	import { onMount } from 'svelte';

	let firstCanvas: HTMLCanvasElement;
	let secondCanvas: HTMLCanvasElement;
	let thirdCanvas: HTMLCanvasElement;
	let newRive: any;

	const createNewRive = (src: string, canvas: HTMLCanvasElement, autoplay: boolean) => {
		console.log('createNewRive');

		try {
			newRive = new Rive({
				src,
				canvas,
				autoplay
			});
		} catch (e) {
			console.log('error: ' + e);
		}
	};

	onMount(() => {
		createNewRive('/ColorF.riv', firstCanvas, true);
		createNewRive('/Blob01.riv', secondCanvas, true);
		createNewRive('/ColorF.riv', thirdCanvas, true);
	});
</script>

<div />

<div class="flex flex-col flex-grow justify-center w-screen ">
	<div class="h-1/2 flex justify-center">
		<div class="flex justify-end items-end h-full w-1/2 -rotate-12">
			<div>
				<canvas id="canvas-01" width="300" height="300" bind:this={firstCanvas} />
			</div>
		</div>

		<div class=" flex justify-start items-end h-full w-1/2 rotate-12">
			<div>
				<canvas id="canvas-02" width="300" height="300" bind:this={secondCanvas} />
			</div>
		</div>
	</div>

	<div class="h-1/2">
		<div class="flex justify-center h-full -rotate-45">
			<div>
				<canvas id="canvas-03" width="300" height="300" bind:this={thirdCanvas} />
			</div>
		</div>
	</div>
</div>
