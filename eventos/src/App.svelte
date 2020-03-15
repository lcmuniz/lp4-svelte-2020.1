<script>
  import Header from "./components/Header.svelte";
  import EventosGrid from "./components/EventosGrid.svelte";
  import TextInput from "./components/TextInput.svelte";
  import Button from "./components/Button.svelte";

  let eventos = [
    {
      id: 1,
      titulo: "Olimpiada de Programação",
      subtitulo: "Aprendendo a programar em 1 hora",
      descricao:
        "Nestas olimpiadas, vários competidores participarão para decidir que é o melhor programador!",
      urlImagem:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSkr1C_MtCh_vX6WRV9zO5Yx-nGKk-oOX3lE_eD7tUBBzkKiIqj",
      endereco: "Avenida Norte, 23 - Centro - São Luís (MA)",
      emailContato: "lcmuniz@gmail.com"
    },
    {
      id: 2,
      titulo: "Semana da Paz",
      subtitulo: "Paz na terra aos homens de boa vontade",
      descricao:
        "Venha participar dos eventos da Semana da Paz. Seja vonluntário.",
      urlImagem:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRbmwVNJHG8qLEolFBdV5k_jN8enZZvsuqldNqLj7ES9oM437QP",
      endereco: "Avenida Beira Mar, 200 - Calhau - São Luís (MA)",
      emailContato: "paz@gmail.com"
    }
  ];

  let titulo = "";
  let subtitulo = "";
  let endereco = "";
  let urlImagem = "";
  let email = "";
  let descricao = "";

  function adicionarEvento() {
    const novoEvento = {
      id: Math.random().toString(),
      titulo: titulo,
      subtitulo: subtitulo,
      endereco: endereco,
      descricao: descricao,
      emailContato: email,
      urlImagem: urlImagem
    };

    eventos = [novoEvento, ...eventos];
  }
</script>

<style>
  main {
    margin-top: 5rem;
  }
  .form {
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>

<Header />

<main>

  <div class="form">
    <TextInput
      id="titulo"
      label="Título"
      value={titulo}
      on:input={event => (titulo = event.target.value)} />
    <TextInput
      id="subtitulo"
      label="Subtítulo"
      value={subtitulo}
      on:input={event => (subtitulo = event.target.value)} />
    <TextInput
      id="endereco"
      label="Endereço"
      value={endereco}
      on:input={event => (endereco = event.target.value)} />
    <TextInput
      id="urlImagem"
      label="URL da Imagem"
      value={urlImagem}
      on:input={event => (urlImagem = event.target.value)} />
    <TextInput
      id="email"
      label="E-Mail"
      value={email}
      tipoControle="email"
      on:input={event => (email = event.target.value)} />
    <TextInput
      id="descricao"
      tipoControle="textarea"
      label="Descrição"
      value={descricao}
      on:input={event => (descricao = event.target.value)} />
    <Button titulo="Salvar" on:click={adicionarEvento} />
  </div>

  <EventosGrid {eventos} />
</main>
