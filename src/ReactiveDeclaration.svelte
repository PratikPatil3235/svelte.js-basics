<script>
  let firstName = "Bruce";
  let lastName = "Wane";
  $: fullName = `${firstName} ${lastName}`;

  let items = [
    { id: 1, title: "TV", price: 100 },
    { id: 2, title: "Phone", price: 200 },
    { id: 3, title: "Laptop", price: 300 },
  ];

  $: total = items.reduce((acc, el) => el.price + acc, 0);

  function changeName() {
    firstName = "Clark";
    lastName = "Kent";
  }

  function addItem() {
    items = [...items, { id: items.length + 1, title: "Keyboard", price: 400 }];
    console.log(items);
  }
</script>

<main>
  <h1>{fullName}</h1>
  <h2>{firstName} {lastName}</h2>

  <h3>Total: ₹{total}</h3>

  <ul>
    {#each items as item}
      <li>{item.title} — ₹{item.price}</li>
    {/each}
  </ul>

  <button on:click={changeName}>Change Name</button>
  <button on:click={addItem}>Add Item</button>
</main>

<style>
  main {
    text-align: center;
    padding: 2em;
    max-width: 400px;
    margin: 2rem auto;
    font-family: "Segoe UI", sans-serif;
    background: #f9f9f9;
    border-radius: 12px;
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 2.5em;
    font-weight: 600;
  }

  h2 {
    margin-top: -1rem;
    color: #555;
  }

  h3 {
    margin-top: 1.5rem;
    color: #4e8cff;
  }

  ul {
    list-style-type: none;
    padding: 0;
    margin: 1rem 0;
  }

  li {
    margin-bottom: 0.4rem;
    font-size: 1rem;
  }

  button {
    margin: 0.5rem;
    padding: 0.6rem 1.2rem;
    font-size: 1rem;
    border: none;
    border-radius: 8px;
    background-color: #4e8cff;
    color: white;
    cursor: pointer;
    transition: 0.2s ease;
  }

  button:hover {
    background-color: #346fd6;
  }
</style>
