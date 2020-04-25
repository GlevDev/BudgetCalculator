<script>
  export let showForm;
</script>

<nav class="nav">
  <div class="nav-center">
    <h1 class="nav-title">Calculer ses dépenses</h1>
    <button type="button" class="nav-btn" on:click={showForm}>
      <i class="far fa-plus-square" />
      Nouvel élément
    </button>
  </div>
</nav>