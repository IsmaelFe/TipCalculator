<script>
  export let result = "$0.00";
</script>

<div class="container">
  <div class="result">
    <div>
      <h3>Tip Amount</h3>
      <span>/ person</span>
    </div>
    <p>{result}</p>
  </div>
  <div class="result">
    <div>
      <h3>Total</h3>
      <span>/ person</span>
    </div>
    <p>$0.00</p>
  </div>
  <button> RESET </button>
</div>

<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    background-color: #01464b;
    width: 50%;
    padding: 25px;
    border-radius: 8px;
    color: white;
  }

  .result {
    display: flex;
    padding: 10px;
    justify-content: space-between;
  }

  span {
    color: #699b9f;
    font-weight: bold;
    font-size: 0.8em;
  }

  p {
    color: #27c0ac;
    font-size: 2em;
    font-weight: 600;
  }

  button {
    color: #034a4f;
    width: 95%;
    font-family: "Space Mono", monospace;
    font-weight: 600;
    background-color: #27c0ac;
    border: none;
    border-radius: 3px;
    padding: 7px;
    margin: 30% auto 0 auto;
  }

  button:hover {
    cursor: pointer;
  }

  h3 {
    font-size: 1em;
  }

  @media (max-width: 1050px) {
    .container {
      width: 85%;
      margin: auto;
    }
  }
</style>
