<script lang="ts">
	const startCountdown = (date: Date) => {
		let now = $state(new Date().getTime());
		let targetDate = date.getTime();

		const x = setInterval(() => {
			now = new Date().getTime();
		}, 1000);

		const diff = $derived(targetDate - now);

		const days = Math.floor(diff / (1000 * 60 * 60 * 24))
			.toString()
			.padStart(2, '0');

		const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
			.toString()
			.padStart(2, '0');

		const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60))
			.toString()
			.padStart(2, '0');

		const seconds = Math.floor((diff % (1000 * 60)) / 1000)
			.toString()
			.padStart(2, '0');

		return `${days}d ${hours}h ${minutes}m ${seconds}s`;
	};
</script>

<main class="h-screen w-full">
	<div class="flex h-full flex-col items-center justify-center gap-4">
		<div class="flex flex-col items-center justify-center">
			<h2 class="text-2xl">🦸Marvel Rivals Season 1 🦸</h2>
			<h1 class="text-3xl tracking-normal">{startCountdown(new Date('2025-01-10T09:00:00Z'))}</h1>
		</div>
		<div class="flex flex-col items-center justify-center">
			<h2 class="text-2xl">🦸Marvel Rivals Twitch Drops🦸</h2>
			<h1 class="text-3xl tracking-normal">{startCountdown(new Date('2025-01-10T12:00:00Z'))}</h1>
		</div>
	</div>
</main>
