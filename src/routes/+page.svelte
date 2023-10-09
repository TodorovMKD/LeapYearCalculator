<script lang="ts">
	let year: number | null = null;
	let isLeapYear: boolean | null = null;

	function checkLeapYear(): void {
		if (!year) {
			alert('Please enter a valid year.');
			return;
		}
		isLeapYear = isLeap(year);
	}

	function isLeap(year: number): boolean {
		return (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
	}
</script>

<div
	class="static container h-full mx-auto flex justify-center items-center flex items-center justify-center h-screen"
>
	<div class="card p-4">
		<div class="space-y-5">
			<label class="label">
				<span>Year:</span>
				<input bind:value={year} class="input" type="text" placeholder="Enter a year..." />
				<button on:click={checkLeapYear} type="button" class="btn variant-filled">Calculate</button>
			</label>
			{#if isLeapYear !== null}
				<p>
					{isLeapYear ? 'It is a leap year.' : 'It is not a leap year.'}
				</p>
			{/if}
		</div>
	</div>
</div>
