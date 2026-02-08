<script>
  import dice1 from "./public/assets/dice-1.png";
  import dice2 from "./public/assets/dice-2.png";
  import dice3 from "./public/assets/dice-3.png";
  import dice4 from "./public/assets/dice-4.png";
  import dice5 from "./public/assets/dice-5.png";
  import dice6 from "./public/assets/dice-6.png";

  let diceResults = $state([1, 1, 1, 1, 1]);

  const diceImages = [dice1, dice2, dice3, dice4, dice5, dice6];

  const generateNumber = () => Math.floor(Math.random() * 6) + 1;

  console.log(diceResults);
</script>

<div style="text-align: center;">
  {#each diceResults as diceResult}
    <img
      src={diceImages[diceResult - 1]}
      alt={diceResult.toString()}
      style="margin-right: 20px;"
    />
  {/each}
</div>

<button
  style="display: block; background-color: rgb(255,219,187); padding: 25px; margin: 10px auto; font-weight: bold"
  onclick={() =>
    (diceResults = Array.from({ length: 5 }, (_, i) => generateNumber()))}
  >Dobás</button
>
