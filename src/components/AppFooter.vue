<template>
  <footer>
    <span>Made with <md-icon>favorite_border</md-icon></span>
    <span><a class="contact" href="mailto:me@leslye.dev"> Contact</a></span>
    <span>
      <a href="https://www.iubenda.com/privacy-policy/81930472" title="Privacy Policy" target="_blank">Imprint</a>
      &nbsp;&nbsp;-&nbsp;&nbsp;
      <a href="//www.iubenda.com/privacy-policy/81930472/legal" title="Show the complete Privacy Policy" target="_blank"
        >Privacy Policy</a
      >
    </span>
  </footer>
</template>

<script>
export default {
  name: 'AppFooter',
};
</script>

<style scoped>
footer {
  margin: 5px 25px;
  font-size: 14px !important;
  display: flex;
  justify-content: space-between;
  align-content: center;
}

span a {
  color: inherit !important;
}

.contact {
  color: #8d69ea !important;
}
</style>
