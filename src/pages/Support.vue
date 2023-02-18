<template>
  <Layout>
    <article>
    <h1>Soupçon Salon needs your support.</h1>
    <p>
      Soupçon Salon is a 501(c)3 nonprofit organization and is 100% volunteer-run. The only way we can sustain ourselves is through tax-deductible donations and memberships (aka, "Partnerships"). If you use the space and/or want to support this project please consider donating or becoming a Partner through the links below.
    </p>
      <p><em><a href="/about/#involvement--partner-benefits">Read more about the Partner benefits</a> (space use, local discounts, etc.) you receive when you subscribe.</em></p>
    <div class="product">
      <h2>Partnership Subscription at $10/month</h2>
      <a href="https://buy.stripe.com/4gwdRp2qw2Q47Be4gg">Subscribe now at $10/month!</a>
    </div>
    <div class="product">
      <h2>Partnership Subscription at $20/month</h2>
      <a href="https://buy.stripe.com/bIY14D9SYgGUaNq28k">Subscribe now at $20/month!</a>
    </div>
    <div class="product">
      <h2>Partnership Subscription at $30/month</h2>
      <a href="https://buy.stripe.com/14kcNl0io0HWg7KbIV">Subscribe now at $30/month!</a>
    </div>
    <div class="product">
      <h2>Partnership Subscription at $40/month</h2>
      <a href="https://buy.stripe.com/fZeeVt6GMcqEcVy8wK">Subscribe now at $40/month!</a>
    </div>
    <div class="product">
      <h2>Make a One-time Donation to Soupçon Salon</h2>
      <a href="https://buy.stripe.com/dR6dRpd5aeyM2gUcMQ">Donate now!</a>
    </div>

    <p class="important-note"><em>
      Please note that all funding goes directly into maintaining the facilities and improving our programming. Here is our current income and expense breakdown.</em><br/>
      <br/>
      <g-image alt="Soupçon Salon Income" src="~/income.png" width="400px" />
      &nbsp;&nbsp;
      <g-image alt="Soupçon Salon Expense" src="~/expenses.png" width="400px" />
    </p>
  </article>
  </Layout>
</template>
<script>
export default {
  metaInfo: {
    title: 'Soupçon Salon - Schedule of Events'
  },
};
</script>

<style>
.product {
  margin-left: 2em;
  margin-right: 4em;
  margin-bottom: 1em;
  padding: .5em 1em 1.5em 1em;
}

.pending {
  opacity: .5;
}

.product:nth-of-type(odd) {
  background: aliceblue;
}

.important-note {
  background: beige;
  padding: 1em;
}

.note {
  padding: 1em;
}

.tag {
  background-color: gray;
  border: 1px solid darkgray;
  border-radius: 2em;
  color: white;
  display: inline-block;
  font-size: 12px;
  font-weight: 500;
  padding: 0 6px;
  text-align: center;
}

.hide {
  display: none;
}

&:empty {
    display: none;
  }
</style>
