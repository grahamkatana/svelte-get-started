<script>
import { createEventDispatcher } from "svelte";


  export let user;
  const dispatch = createEventDispatcher()
  const remove = () =>{
    dispatch('remove',user.id)

  }
</script>

<div
  class="relative flex m-5  bg-white border p-2 rounded-lg shadow-md hover:shadow-lg cursor-pointer items-center"
>
  <button on:click={remove}
    class="absolute right-0 top-0 -mt-3 rounded-full w-5 h-5 bg-red-300 text-white text-sm text-center hover:bg-red-700"
    >X</button
  >
  <p class="w-10">{user.id}</p>
  <img
    class="rounded-full w-18 h-14"
    src={user.userImage}
    alt={user.userName}
  />
  <p class="mx-4 w-20">{user.userName}</p>
  <p class="mx-4 w-20">{user.userEmail}</p>
</div>
