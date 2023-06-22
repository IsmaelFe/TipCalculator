<script>
  import Icon1 from "../../assets/icon-dollar.svg";
  import Buttons from "../Buttons.svelte";
  import Result from "../Result.svelte";
</script>

<div class="container-main">
  <div class="container">
    <label for="b">Bill</label>
    <input type="number" id="b" placeholder="0" />
    <h4>Select Tip %</h4>
    <Buttons />
    <label for="n">Number of People</label>
    <input type="number" id="n" placeholder="0" />
  </div>
  <Result />
</div>

<style scoped>
  .container-main {
    display: flex;
    gap: 10px;
    width: 40%;
    height: 350px;
    background-color: white;
    padding: 15px;
    border-radius: 15px;
  }

  .container {
    display: flex;
    padding: 10px;
    flex-direction: column;
    justify-content: space-around;
    gap: 23px;
  }

  input {
    border: none;
    width: 95%;
    background-color: #f3f8fb;
    text-align: end;
    padding: 8px;
    border-radius: 3px;
    margin-top: -15px;
    font-family: "Space Mono", monospace;
    font-weight: 600;
    appearance: textfield;
  }

  input:hover {
    cursor: pointer;
  }

  input::placeholder {
    color: #9cb5b4;
  }

  input:focus {
    outline: 2px solid #58aa9c;
  }

  input::-webkit-inner-spin-button,
  input::-webkit-outer-spin-button {
    display: none;
  }

  label {
    color: #60787b;
    font-size: 0.8em;
    font-weight: 600;
  }

  h4 {
    color: #60787b;
    font-size: 0.8em;
    font-weight: 600;
  }

  @media (max-width: 1050px) {
    .container-main {
      flex-direction: column;
      width: 93%;
      border-radius: 30px 30px 0 0;
      height: 100%;
    }
  }
</style>
