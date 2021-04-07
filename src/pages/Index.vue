<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/soupcon.png" width="1000" />

    <h1>Soupçon Salon is back!</h1>
    <p>
      Soupçon Salon was a wildly successful experiment that celebrated the local community
      through food and art. Today, we are happy to announce that Soupçon is reborn as an arts-focused mutual aid collective.
      We intend to turn what was a single evening of sharing a meal, coupled
      with local entertainment into a much broader and more meaningful experience.
    </p>
    <p>
      Soupçon Salon will reopen at 19 N. Union Street (formerly Manon) this summer as a not-for-profit
      Beneficiary Society (501c8). Please read more about how it works in the <g-link to="/about/">How it Works</g-link> section. If you
      are ready to hear more, please join our mailing list below.
    </p>
    <blockquote>"Everything worthwhile is done with others,"<br/>
      -Moussa Kaba, Guinea independence activist and father of Miriame Kaba
    </blockquote>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/veN9EYsV_LU"
    title="YouTube video player" frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen></iframe>

  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Soupçon Salon'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
img {
  max-width: 100%;
  height: auto;
}
</style>
