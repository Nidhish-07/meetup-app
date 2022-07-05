<script>
  import MeetUpPlace from "./MeetUpPlace.svelte";
  export let meetups;
</script>

<section id="meetups">
  {#each meetups as meetup}
    <MeetUpPlace
      title={meetup.title}
      imageUrl={meetup.imageUrl}
      description={meetup.description}
      address={meetup.address}
      email={meetup.email}
    />
  {/each}
</section>

<style>
  section {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  @media (min-width: 768px) {
    section {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>
