<script>
</script>

<div>
  <button>5%</button>
  <button>10%</button>
  <button>15%</button>
  <button>25%</button>
  <button>50%</button>
  <input type="text" placeholder="Custom" />
</div>

<style scoped>
  div {
    display: grid;
    grid-template-columns: repeat(3, 30%);
    gap: 12px;
  }

  button {
    font-family: "Space Mono", monospace;
    font-weight: 500;
    font-size: 1em;
    color: white;
    background-color: #01464d;
    border: none;
    border-radius: 3px;
    padding: 6px 12px;
  }

  button:hover {
    cursor: pointer;
  }

  input {
    color: #547876;
    font-weight: 600;
    background-color: #f3f8fb;
    border: none;
    border-radius: 3px;
    padding: 10px;
    text-align: center;
    font-family: "Space Mono", monospace;
  }

  input:hover {
    cursor: pointer;
  }

  input::placeholder {
    color: #587472;
  }

  input[type="text"]:focus {
    outline: 2px solid #58aa9c;
  }
</style>
