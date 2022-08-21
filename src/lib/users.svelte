<script>
  import { each } from "svelte/internal";
  import Filteruser from "./filteruser.svelte";
  import Newuser from "./newuser.svelte";
  import User from "./user.svelte";

  let users = [
    {
      id: 1,
      userImage:
        "https://imgs.search.brave.com/0-2bUridYIxGULWqW19DilNUoiv92MDGoa1s8jml1Aw/rs:fit:641:225:1/g:ce/aHR0cHM6Ly90c2Ux/Lm1tLmJpbmcubmV0/L3RoP2lkPU9JUC41/MlQ4SEhCV2g2YjBk/d3JHNnRTcFZRSGFG/ZSZwaWQ9QXBp",
      userName: "John Doe",
      userEmail: "johndoe@gmail.com",
      active: true,
    },
    {
      id: 2,
      userImage:
        "https://imgs.search.brave.com/0-2bUridYIxGULWqW19DilNUoiv92MDGoa1s8jml1Aw/rs:fit:641:225:1/g:ce/aHR0cHM6Ly90c2Ux/Lm1tLmJpbmcubmV0/L3RoP2lkPU9JUC41/MlQ4SEhCV2g2YjBk/d3JHNnRTcFZRSGFG/ZSZwaWQ9QXBp",
      userName: "John Doe",
      userEmail: "johndoe@gmail.com",
      active: false,
    },
  ];

  let filteredList = users;

  const getUsers = () => {
    return users;
  };

  const filterUsers = ({ detail }) => {
    if (detail == "null") {
      return (filteredList = users);
    }
    const status = detail == "true";
    filteredList = users.filter((user) => user.active == status);
  };

  const remove = ({ detail }) => {
    users = users.filter((user) => user.id != detail);
    return (filteredList = users);
  };
</script>

<div>
  <h1 class="text-2xl text-center mt-10">List of users</h1>
  <div class="flex justify-between mx-4 items-center">
    <Filteruser on:filterUsers={filterUsers} />
    <Newuser />
  </div>

  {#each filteredList as user, i (user.id)}
    <User on:remove={remove} {user} />
  {:else}
    <p class="text-2xl text-center mt-10">No users found</p>
  {/each}
</div>
