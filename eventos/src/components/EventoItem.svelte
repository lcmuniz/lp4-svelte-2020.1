<script>
  import Button from "../components/Button.svelte";

  export let titulo;
  export let subtitulo;
  export let urlImagem;
  export let descricao;
  export let endereco;
  export let email;
</script>

<style>
  .card {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    border-radius: 5px;
    background-color: white;
    margin: 1rem;
  }

  header,
  .conteudo,
  footer {
    padding: 1rem;
  }

  .conteudo {
    text-align: right;
    height: 4rem;
  }

  .imagem {
    width: 100%;
    height: 14rem;
  }

  .imagem img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  h1 {
    font-size: 1.25rem;
    margin: 0.5rem 0;
  }

  h1.eh-favorito {
    background: #01a129;
    color: white;
    padding: 0 0.5rem;
    border-radius: 5px;
  }

  h2 {
    font-size: 1rem;
    color: #808080;
    margin: 0.5rem 0;
  }

  p {
    font-size: 1.25rem;
    margin: 0;
  }
</style>

<div class="card">
  <header>
    <h1>{titulo}</h1>
    <h2>{subtitulo}</h2>
    <p>{endereco}</p>
  </header>
  <div class="imagem">
    <img src={urlImagem} alt={titulo} />
  </div>
  <div class="conteudo">
    <p>{descricao}</p>
  </div>
  <footer>
    <Button href="mailto:{email}" titulo="Contato" />
    <Button titulo="Mostrar Detalhes" />
    <Button titulo="Favorito" mode="outline" />
  </footer>
</div>
