<template>
  <Layout>
    <article style="grid-column: 1 / span 2;">
      <div class="welcome">
      <h1>The idea is simple:</h1>
      <p>Build community and promote healing by gathering together
        to share food, tell stories, make art, and fill the air with music.
        We work towards collective excellence, and facilitate a voluntary reciprocal
        exchange of resources for mutual benefit. This is a radical experiment
        in creating utopia.</p>
        <p>You are hereby invited.</p>
      </div>
    </article>

    <!-- full width -->
    <div class="media" style="grid-column: 1 / span 3;">
      <iframe width="100%" height="600px" src="https://www.youtube.com/embed/veN9EYsV_LU"
      title="YouTube video player" frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen></iframe>
    </div>
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
