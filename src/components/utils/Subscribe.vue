<script>
export default {};
</script>

<template>
  <form
    action="https://buttondown.email/api/emails/embed-subscribe/jasontcrabtree"
    method="post"
    target="popupwindow"
    onsubmit="window.open('https://buttondown.email/jasontcrabtree', 'popupwindow')"
    class="subscribe-form--style tinyletter-sub-form"
  >
    <p>
      Subscribe to receive emails about new blog posts.
      I write about learning Product Design and business design strategy analysis.
    </p>
    <fieldset class="subscribe-form-fieldset--layout sub-fieldset--style">
      <label class="subscribe-label--style" for="bd-email">Your Email</label>
      <input
        placeholder="hello@email.com"
        type="email"
        name="email"
        id="bd-email"
        class="subscribe-email-input"
      />
    </fieldset>
    <input type="hidden" value="1" name="embed" />
    <button class="newsletter" type="submit" value="Subscribe">Subscribe</button>
  </form>
</template>

<style>
fieldset {
  margin: 8px 0px;
}

.sub-fieldset--style {
  border: 0px;
  padding: 0px;
  margin: 0px;
}

.subscribe-form-fieldset--layout {
  margin: 24px 0px;
}

.tinyletter-sub-form > * > input {
  max-width: 32ch;
  width: 100%;
  height: 48px;
  padding: 8px;
  border: 1px solid var(--grey-200);
  border-radius: 4px;
}

.subscribe-credit--style {
  font-size: var(--size-16);
}

@media screen and (max-width: 460px) {
  .subscribe-email-input {
    width: 80vw;
  }
}
</style>