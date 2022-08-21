<script>
  import Modal from "./modal.svelte";
  let showModal = false;
</script>

<div class="mt-4">
  <button
    on:click={() => (showModal = true)}
    class="px-8 py-3  bg-purple-800 text-white rounded-lg ">Add User</button
  >
  {#if showModal}
    <Modal on:close={() => (showModal = false)}>
      <div class="py-1 px-2 my-4">
        <label class="w-10" for="">Name</label>
        <input class="px-2 py-2 rounded border" type="text" placeholder="Name" />
      </div>
      <button
        slot="create-button"
        type="submit"
        class="px-2 py-1 bg-green-400 taxt-white rounded">Create</button
      >
    </Modal>
  {/if}
</div>
