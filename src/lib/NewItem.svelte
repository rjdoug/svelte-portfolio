<!-- Input container to specify content of a new list item -->
<script>
    import { createEventDispatcher } from "svelte";
  
    const dispatch = createEventDispatcher();
    let value = "";
  
    /**
     * If input is valid call newItem in parent and pass given value
     * @param key event key pushed
     */
    function handleKeyUp({ key }) {
      if (key !== "Enter" || value.length === 0) return;
      dispatch("newItem", value);
      value = "";
    }
  </script>
  
  <input type="text" on:keyup={handleKeyUp} bind:value placeholder="+ Add Item" />
  
  <style>
    input {
      box-sizing: border-box;
      margin-bottom: 15px;
      padding: 15px;
      border: none;
      outline: none;
      width: 100%;
      background: rgba(0, 0, 0, 0.25);
      color: #fff;
      font-weight: bold;
      font-size: 1em;
      cursor: pointer;
    }
  
    input::placeholder {
      color: #fff;
    }
  </style>
  