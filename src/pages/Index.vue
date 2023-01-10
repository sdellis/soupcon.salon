<template>
  <Layout>
    <article style="grid-column: 1 / span 2;">
      <div class="welcome">
      <h1>Our Mission:</h1>
      <p>Soupçon Salon provides a space that unites people to build a more beautiful and equitable world.</p>
      <p>We connect people through art, music and creative expression, health and wellness, community organizations,
        social connections, mutual aid, and education.</p>
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
