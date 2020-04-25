<script>
  import SectionTitle from "./Title.svelte";
  import Expense from "./Expense.svelte";
  export let expenses = [];
</script>

<style>
h2 {
  text-transform: capitalize;
}
</style>

<section>
  <SectionTitle title="Liste des dépenses" />
  <ul>
    {#each expenses as expense}
      <Expense {...expense} />
    {:else}
    <h2>Aucune dépense</h2>
    {/each}
  </ul>
</section>
