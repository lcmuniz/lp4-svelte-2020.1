<script>
  import EventoItem from "../components/EventoItem.svelte";

  export let eventos;
</script>

<style>
  section {
    width: 100%;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 1rem;
  }
</style>

<section id="eventos">
  {#each eventos as evento}
    <EventoItem
      titulo={evento.titulo}
      subtitulo={evento.subtitulo}
      urlImagem={evento.urlImagem}
      descricao={evento.descricao}
      endereco={evento.endereco}
      email={evento.emailContato} />
  {/each}
</section>
