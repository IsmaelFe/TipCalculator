<script>
  import App_container from "./components/container/App_container.svelte";
  import Icon from "./assets/logo.svg";
</script>

<main>
  <img src={Icon} alt="Logo" />
  <App_container />
</main>

<style scoped>
  img {
    width: 70px;
    height: 40px;
    margin-bottom: 50px;
  }

  main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100%;
    background-color: #c4e4e6;
  }

  @media (max-width: 1050px) {
    main {
      height: 100%;
    }

    img {
      margin: 50px auto 30px auto;
    }
  }
</style>
