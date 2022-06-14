<template>
  <section>
      <div class="wrapper">
        <header id="header">
        <div class="logo-box">
            <g-image class="logo" alt="Soupçon Salon" src="~/heart-arrow.png" width="32px" />
          <strong>
            <g-link class="logotype" to="/">{{ $static.metadata.siteName }}</g-link>
          </strong>
        </div>
          <nav class="nav">
            <g-link class="nav__link" to="/">Home</g-link>
            <g-link class="nav__link" to="/schedule/">Schedule</g-link>
            <g-link class="nav__link" to="/about/">How it Works</g-link>
            <!--<g-link class="nav__link" to="/about/">How it Works</g-link>-->
            <!-- <g-link class="nav__link" to="https://soupcon-salon.square.site/">Become a Partner</g-link> -->
            <g-link class="nav__link" to="https://buy.stripe.com/4gwdRp2qw2Q47Be4gg">Become a Partner</g-link>
          </nav>
        </header>
        <div class="subheader">
          <!--<p><em>"Everything worthwhile is done with others," -Moussa Kaba</em>
          </p>-->
          <p style="color: #FD4659;">
            Soupçon Salon announces new location at the former Hibernia Firehouse, at 37 South Main Street!
          </p>
        </div>
        <main>
          <slot/>
        </main>
        <footer>
          <!-- Begin Mailchimp Signup Form -->
            <link href="//cdn-images.mailchimp.com/embedcode/horizontal-slim-10_7.css" rel="stylesheet" type="text/css">
            <div id="mc_embed_signup">
            <form action="https://sdellis.us1.list-manage.com/subscribe/post?u=5c1b92d020d829ab83b323a4a&amp;id=260568367e" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
                <div id="mc_embed_signup_scroll">
            	<label for="mce-EMAIL">Subscribe to our Newsletter</label>
            	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
                <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
                <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_5c1b92d020d829ab83b323a4a_260568367e" tabindex="-1" value=""></div>
                <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
                </div>
            </form>
            </div>

            <!--End mc_embed_signup-->
        </footer>
  </div>
</section>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
@import url('https://fonts.googleapis.com/css2?family=Averia+Serif+Libre:wght@300&display=swap');

html {
  height: 100%;
  scroll-behavior: smooth;
}
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  /* font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif; */
  margin:0;
  padding:0;
  line-height: 1.5;
  background-color: #fff;
  color: #333;
  height: 100%;
}
h1 {
  font-family: "Averia Serif Libre",Georgia,Times,"Times New Roman",serif;
  margin-bottom: 1.25rem;
}

h1,h2,h3,h4,h5,h6 {
  color: #FD4659;
}
article h1 {
  font-size: 2em;
}
a {
  color: #333;
}

.wrapper {
     min-height: 100%;
     display: grid;
     grid-template-rows: auto;
     grid-template-columns: auto;
     grid-gap: 1em;
     grid-template-areas: "header"
                        "main"
                        "media"
                        "footer";
}

header {
  grid-area: header;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  height: auto;
  background-color: #f5f5f5;
  color: #111;
  padding: 2rem;
}

.subheader {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  height: auto;
  border-bottom: 1px solid #efefef;
  margin-right: 2rem;
  margin-left: 2rem;
}

.logo-box {
   display: flex;
   align-items:center;
}

footer {
  /* grid-area: footer; */
  background: #f5f5f5;
  color: #333;
  padding: 20px;
}

.nav__link {
  margin-left: 20px;
}

.logotype {
  font-family: "Averia Serif Libre",Georgia,Times,"Times New Roman",serif;
  font-size: 32px;
  text-decoration: none;
  padding: .25em;
}

.logo {
  margin-top: -8px;
}

/* Styles for sub-pages */

main {
  /* min-height: 100%; */
  display: grid;
  grid-template-columns: 0px auto 0px;
  grid-template-rows: auto 1fr auto;
  grid-template-areas: "sidebar-2" "article" "sidebar-1";
  grid-gap: 1rem;
}

/* @media screen and (min-width: 600px) {
  main {
    grid-template-columns: 0px auto 250px;
    grid-template-areas: "sidebar-1 article sidebar-2";
  }
  .sidebar-right {
    display: block;
  }
} */

.sidebar-right {
  grid-area: sidebar-2;
  padding-right: 20px;
  position: sticky;
  top: 0;
  height: 100vh;
  box-sizing: border-box;
  display: none;
}

.sidebar-left {
  grid-area: sidebar-1;
  padding-left: 20px;
  display: none;
}

article {
  grid-area: article;
  margin-top: -3rem;
  padding: 2rem;
  grid-column: 1 / span 3;
}

.media {
  grid-area: media;
  height:auto;
  grid-column: 1 / span 3;
  grid-row: 4 / 5;
}

@media screen and (min-width: 900px) {
  header {
    margin-bottom: -20px;
    height: 80px;
  }
  .welcome {
    max-width: 500px;
    padding: 2rem;
  }
  .subheader {
    height: 80px;
  }
  main>article {
      grid-column: article;
  }
  article {
    padding: 0;
    grid-column: 2 / span 1;
  }
  media {
    padding: 0;
    grid-column: 2 / span 1;
  }
  .sidebar-right {
    display: block;
  }

  .sidebar-left {
    display: block;
  }
  main {
    grid-template-columns: 250px auto 250px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas: "sidebar-1 article sidebar-2";
  }
}

.full-width {
  grid-area: full;
  height:auto;
  grid-column: 1 / span 3;
  grid-row: 1 / 2;
}

/* Full is using for full width out of the container */
main>div.full-width {
    grid-column: full;
}

/* Scrollspy nav */

/* 2. Make nav sticky */
main > nav {
  position: sticky;
  top: 2rem;
  align-self: start;
}

/* 3. ScrollSpy active styles (see JS tab for activation) */
.section-nav li.active > a {
  color: #333;
  font-weight: 500;
}

/* Sidebar Navigation */
.section-nav {
  margin-left: 2rem;
  padding-top: 1rem;
  border-left: 1px solid #efefef;
}

.section-nav a {
  text-decoration: none;
  display: block;
  padding: .125rem 0;
  color: #ccc;
  transition: all 50ms ease-in-out; /* 💡 This small transition makes setting of the active state smooth */
}

.section-nav a:hover,
.section-nav a:focus {
  color: #666;
}

/** Poor man's reset **/
* {
  box-sizing: border-box;
}

nav h1 {
  font-weight: 300;
}

nav ul, ol {
  list-style: none;
  margin: 0;
  padding: 0;
}

li {
  margin-left: 1rem;
}

</style>
