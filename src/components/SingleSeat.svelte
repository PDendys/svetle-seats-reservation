<script lang="ts">
    import { getContext, onMount } from 'svelte';

    export let seatId;

    let isActive = false;
    let isSeatTaken = false;

    const seatsData: { busySeats: string[] } = getContext('seatsManagerData')

    const { busySeats } = seatsData || {};

    onMount(() => {
        if (isSeatAlreadyTaken()) {
            isSeatTaken = true;
        }
    })
    
    const isSeatAlreadyTaken = (): boolean => {
        return busySeats && busySeats.includes(seatId);
    }

    const onSeatClick = (): void => {
        if (!isSeatAlreadyTaken()) {
            isActive = !isActive;
        }
    }
</script>

<div class="seat" class:taken={isSeatTaken} class:choosed={isActive} on:click={onSeatClick}>
    { seatId }
</div>

<style>
    .seat {
        background-color: #dddddd;
        color: #333333;
        padding: 5px 10px;
        margin: 0 3px 6px;
        cursor: pointer;
        width: 30px;
        height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .seat.taken {
        background-color: #716565;
        color: #fff;
        cursor: not-allowed;
    }

    .seat.choosed {
        background-color: chartreuse;
        color: #fff;
    }
</style>
