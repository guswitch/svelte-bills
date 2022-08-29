<!-- svelte-ignore a11y-label-has-associated-control -->
<script lang="ts">
  import { Bill } from "../types/bill";

  let bill = {} as Bill;
  let isDisable = true;

  const handleSubmit = () => {
    let createdBills: Bill[] = JSON.parse(localStorage.getItem('bills'))

    if(createdBills){
        createdBills.push(bill)
        localStorage.setItem('bills', JSON.stringify(createdBills))
    } else {
        localStorage.setItem('bills', JSON.stringify([bill]))
    }
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <div class="form-item">
    <label htmlfor="bill-name">Name</label>
    <input type="text" name="bill-name" id="bill-name" bind:value={bill.name} />
  </div>
  <div class="form-item">
    <label htmlfor="bill-name">Description</label>
    <textarea maxlength="150" name="bill-desc" bind:value={bill.description} />
  </div>
  <div class="form-item">
    <label htmlfor="bill-name">Payday</label>
    <input type="date" name="bill-date" bind:value={bill.payday} />
  </div>
  <div class="form-item">
    <label htmlfor="bill-name">Price</label>
    <input type="number" name="bill-price" bind:value={bill.price} />
  </div>
  <div class="form-item">
    <input type="submit" value="Add" disabled={isDisable} />
  </div>
</form>
