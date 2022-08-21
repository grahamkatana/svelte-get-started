<script>
import { createEventDispatcher } from "svelte";


    const dispatch = createEventDispatcher()

    // export let filterUsers
    const filterUsers = (e) =>{
        //dispatch an event
        dispatch('filterUsers',e.target.value)
    }
</script>
<div class="ml-4 mt-4">
    <label for="user-filter">Filter users</label>
    <select on:change={filterUsers} name="user-filter" class="border rounded-lg px-4 p-2 ml-4 w-100">
      <option value={null}>All Users</option>
      <option value={true}>Active</option>
      <option value={false}>Inactive</option>
    </select>
    
  </div>