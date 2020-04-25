<script>
  import Title from "./Title.svelte";
  export let name = "";
  export let amount = null;
  export let isEditing = false;
  export let editExpense;
  export let addExpense;
  export let hideForm;
  $: isEmpty = !name || !amount;
  function handleSubmit() {
    if(isEditing) {
      editExpense({name, amount});
    } else {
      addExpense({ name, amount });
    }
    name = "";
    amount = null;
  }
</script>

<section class="form">
  <Title title="Ajouter une dépense" />
  <form class="expense-form" on:submit|preventDefault={handleSubmit}>
    <div class="form-control">
      <label for="name">nom</label>
      <input type="text" id="name" bind:value={name} />
    </div>
    <div class="form-control">
      <label for="amount">montant</label>
      <input type="number" id="amount" bind:value={amount} />
    </div>
    {#if isEmpty}
      <p class="form-empty">Merci de remplir l'ensemble des champs</p>
    {/if}
    <button
      type="submit"
      class="btn btn-block"
      disabled={isEmpty}
      class:disabled={isEmpty}>
      {#if isEditing}Modifier{:else}Ajouter{/if}
    </button>
    <button type="button" class="close-btn" on:click={hideForm}>
      <i class="fas fa-times" />
      <span>fermer</span>
    </button>
  </form>
</section>
