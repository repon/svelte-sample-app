<script lang="ts">
  import { onMount } from 'svelte';
  let time = new Date()


  const zeroBinding = (num: number):string => num.toString().padStart(2, "0")

  $: hours = zeroBinding(time.getHours());
	$: minutes = zeroBinding(time.getMinutes());
	$: seconds = zeroBinding(time.getSeconds());

  onMount(() => {
    const interval = setInterval(() => {
      time = new Date()
    }, 1000);
    return () => clearInterval(interval)
  })

</script>

<div class="clock">
  <time>{hours}:{minutes}:{seconds}</time>
</div>

<style>
.clock {
  font-size: 4em;
  font-variant-numeric: tabular-nums;
}
</style>