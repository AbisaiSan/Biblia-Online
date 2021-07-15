<template>
  <div class="w-1/2 mx-auto my-20">
    <h1 class="text-3xl font-semibold text-red-600">{{ tituloBlog }}</h1>

    <article class="my-20">
      <h2>Informações do livro</h2>
      <h4 class="text-5xl font-semibold mb-5">
        Livro: {{ listaArtigos.book.name }}
      </h4>
      <h4 class="text-5xl font-semibold mb-5">
        Autor: {{ listaArtigos.book.author }}
      </h4>
      <h4 class="text-5xl font-semibold mb-5">
        Gênero Literario: {{ listaArtigos.book.group }}
      </h4>
      <h4 class="text-5xl font-semibold mb-5">
        Versão: {{ listaArtigos.book.version }}
      </h4>

      <p class="mb-5">Capitulo: {{ listaArtigos.chapter.number }}</p>
      <p class="mb-5">Versiculos: {{ listaArtigos.chapter.verses }}</p>
      <p class="mb-5">Texto:{{ listaArtigos.verses.text }}</p>
     
    </article>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      listaArtigos: [],
      tituloBlog: "Biblia Online",
    }
  },
  created() {
    this.fetch();
  },
  methods: {
    async fetch() {
      this.listaArtigos = await fetch(
        "https://www.abibliadigital.com.br/api/verses/nvi/rm/9"
      ).then((res) => res.json());
    },
  },
};
</script>
