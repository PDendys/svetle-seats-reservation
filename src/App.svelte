<script lang="ts">
	import SeatsManager from "./components/SeatsManager.svelte";
	import SingleSeat from "./components/SingleSeat.svelte";

	const seats = [...Array(173).keys()].slice(1);
	const seatsData={ busySeats: ['a1', 'a2', 'a4'] };


</script>

<main>
	<div>
		<h2>Sala kameralna</h2>
		<SeatsManager {seatsData}>
			<div class="row">
				<SingleSeat seatId={'a1'} />
				<SingleSeat seatId={'a2'} />
				<SingleSeat seatId={'a3'} />
				<SingleSeat seatId={'a4'} />
				<SingleSeat seatId={'a5'} />
				<SingleSeat seatId={'a6'} />
			</div>
			<div class="row">
				<SingleSeat seatId={'b1'} />
				<SingleSeat seatId={'b2'} />
				<SingleSeat seatId={'b3'} />
				<SingleSeat seatId={'b4'} />
				<SingleSeat seatId={'b5'} />
				<SingleSeat seatId={'b6'} />
			</div>
			<div class="row">
				<SingleSeat seatId={'c1'} />
				<SingleSeat seatId={'c2'} />
				<SingleSeat seatId={'c3'} />
			</div>
		</SeatsManager>
	</div>
	<hr>
	<div>
		<h2>Sala duża</h2>
		<SeatsManager>
			{#each seats as seat}
				<SingleSeat seatId={seat} />
			{/each}
		</SeatsManager>
	</div>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.row {
		width: 100%;
		display: flex;
		justify-content: center;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.btn {
		background-color: #ff3e00;
		color: #fff;
		border: none;
		border-radius: 5px;
		cursor: pointer;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
