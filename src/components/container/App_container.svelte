<script>
  import Icon1 from "../../assets/icon-dollar.svg";
  import Buttons from "../Buttons.svelte";
  import Result from "../Result.svelte";

  let empty1 = null;
  let empty2 = null;
  let value1 = false;
  let value2 = false;
  let isActive = false;
  let custom = "";
  let result;
  let operator;
  let operation;

  function functionBill(e) {
    empty1 = Number(e);
  }

  function functionPeople(e) {
    empty2 = Number(e);
  }

  function presion(e) {
    operator = e.detail;

    if (empty1 === null || empty2 === null) {
      if (empty2 === null && empty1 === null) {
        value1 = true;
        value2 = true;
      } else if (empty1 === null) {
        value1 = true;
      } else {
        value2 = true;
      }
    } else {
      let temp1;
      let temp2;
      value2 = false;
      value1 = false;
      isActive = true;
      temp1 = (empty1 / 100) * operator;
      operation = temp1.toFixed(2);
      temp2 = (empty1 + temp1) / empty2;
      result = temp2.toFixed(2);
    }
  }

  function functionReset() {
    operation = "0.00";
    result = "0.00";
    empty2 = null;
    empty1 = null;
    isActive = false;
    custom = " ";
  }
</script>

<div class="container-main">
  <div class="container">
    <label for="b"
      >Bill
      {#if value1}
        <span>Can't be zero</span>
      {/if}
    </label>
    <input
      type="number"
      id="b"
      placeholder="0"
      value={empty1}
      on:keyup={(e) => functionBill(e.target.value)}
      class={value1 ? "inactive" : "active"}
    />
    <h4>Select Tip %</h4>
    <Buttons on:pressed={presion} {custom} />
    <label for="n"
      >Number of People
      {#if value2}
        <span>Can't be zero</span>
      {/if}
    </label>
    <input
      type="number"
      id="n"
      placeholder="0"
      value={empty2}
      on:keyup={(e) => {
        functionPeople(e.target.value);
      }}
      class={value2 ? "inactive" : "active"}
    />
  </div>
  <Result {result} {operation} {isActive} on:reset={functionReset} />
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

  .active {
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

  .inactive {
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
    border: solid 2px #db7e6b;
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
    display: flex;
    justify-content: space-between;
    color: #60787b;
    font-size: 0.8em;
    font-weight: 600;
  }

  h4 {
    color: #60787b;
    font-size: 0.8em;
    font-weight: 600;
  }

  span {
    font-size: 1em;
    color: #db7e6b;
    font-family: "Space Mono", monospace;
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
