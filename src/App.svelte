<script>
  import Header from "./UI/Header.svelte";
  import MeetUpPlace from "./meetup/MeetUpPlace.svelte";
  import MeetUpGrid from "./meetup/MeetUpGrid.svelte";
  import FormInput from "./UI/FormInput.svelte";

  let meetups = [
    {
      id: 1,
      title: "Cafe",
      description: "A place to relax and think",
      imageUrl:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRZnKWfY33TRRF-ZkeLnJBhqUg1yR5MG9-l6w&usqp=CAU",
      address: "Stanze Living, Banglore",
      email: "cafe@gmail.com",
    },
    {
      id: 2,
      title: "Swimming Pool",
      description: "A place enjoy",
      imageUrl:
        "https://content3.jdmagicbox.com/comp/def_content/swimming_pools/default-swimming-pools-2.jpg?clr=4b3b1b",
      address: "Jawahar Nagar, Nagpur",
      email: "pool@gmail.com",
    },
    {
      id: 3,
      title: "Park",
      description: "A place to socialize",
      imageUrl:
        "https://static.toiimg.com/thumb/msid-77460303,imgsize-1285842,width-400,resizemode-4/77460303.jpg",
      address: "Ashoka Hotel, New Delhi",
      email: "park@gmail.com",
    },
  ];

  let title = "";
  let address = "";
  let email = "";
  let imageUrl = "";
  let description = "";

  const addMeetup = function () {
    const newMeetup = {
      id: Math.random(),
      title,
      description,
      imageUrl,
      email,
      address,
    };

    meetups = [newMeetup, ...meetups];
  };
</script>

<Header />

<main>
  <MeetUpGrid {meetups} />
  <form on:submit|preventDefault={addMeetup}>
    <FormInput
      id="title"
      labelName="Title"
      value={title}
      on:input={(event) => (title = event.target.value)}
    />
    <FormInput
      id="address"
      labelName="Address"
      value={address}
      on:input={(event) => (address = event.target.value)}
    />
    <FormInput
      id="imageUrl"
      labelName="Image URL"
      value={imageUrl}
      on:input={(event) => (imageUrl = event.target.value)}
    />
    <FormInput
      id="email"
      labelName="Email"
      value={email}
      on:input={(event) => (email = event.target.value)}
    />
    <FormInput
      id="description"
      labelName="Decription"
      value={description}
      on:input={(event) => (description = event.target.value)}
      inputType="textarea"
      rows="4"
    />

    <button type="submit">Add</button>
  </form>
</main>

<style>
  main {
    margin-top: 6rem;
  }

  form {
    width: 30rem;
    max-width: 90%;
    margin: 0 auto;
    margin-top: 3rem;
    padding: 2rem;
    border: 2px dashed #f28891;
  }
</style>
