<script>
  import Icon1 from "../../assets/icon-dollar.svg";
  import Buttons from "../Buttons.svelte";
  import Result from "../Result.svelte";
</script>

<div>
  <div class="container">
    <label for="b">Bill</label>
    <input type="text" id="b" placeholder="0" />
    <h4>Select Tip %</h4>
    <Buttons />
    <label for="n">Number of People</label>
    <input type="text" id="n" placeholder="0" />
  </div>
  <Result />
</div>

<style scoped>
  div {
    display: flex;
    gap: 10px;
    width: 40%;
    height: 50%;
    background-color: white;
    padding: 15px;
    border-radius: 15px;
  }

  .container {
    display: flex;
    flex-direction: column;
    gap: 23px;
  }

  input {
    border: none;
    background-color: #f3f8fb;
    text-align: end;
    padding: 8px;
    border-radius: 3px;
    margin-top: -15px;
    font-family: "Space Mono", monospace;
    font-weight: 600;
  }

  input::placeholder {
    color: #9cb5b4;
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
</style>
