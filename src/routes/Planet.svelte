<script lang="ts">
	export let name: string;
	export let color: string;
	export let radius: number;
	export let orbits: number;
	export let distance: number;
	export let time: number;

	const TAU = 2 * Math.PI;
	const CYCLE_TIME = 10_000;

 	$:cx = calculateX(time);
 	$:cy = calculateY(time);

 function calculateX(time: number): number {
	 return Math.cos((time * TAU * orbits) / CYCLE_TIME) * distance + 500 ;
 }

 function calculateY(time: number): number {
	 return Math.sin((time * TAU * orbits) / CYCLE_TIME) * distance + 500 ;

 }
</script>

<circle cx="500" cy="500" r="{distance}" stroke="#2d3359" fill="none" />
<circle id="{name}" cx="{cx}" cy="{cy}" r="{radius}" fill="{color}" />
