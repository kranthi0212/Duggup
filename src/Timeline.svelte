<!-- Timeline.svelte -->
<script>
  // Sample data for the timeline
  let timelineData = [
    { date: "Dec 2023", details: "Event details here...", imageUrl: "event1.jpg" },
    { date: "Jan 2024", details: "Event details here...", imageUrl: "event2.jpg" },
    { date: "Feb 2024", details: "Event details here...", imageUrl: "event3.jpg" },
  ];
</script>

<style>
  .timeline {
    position: relative;
    width: 100%;
  }

  .event {
    display: flex;
    align-items: flex-start;
    margin-bottom: 20px;
  }

  .date {
    width: 150px; 
    font-weight: bold;
    text-align: right;
    padding-right: 20px;
  }

  .line {
    position: absolute;
    left: calc(150px + 10px); 
    top: 0;
    bottom: 0;
    width: 2px; 
    background-color: #ccc; 
  }

  .details {
    margin-left: 30px; 
    padding-left: 20px; 
  }

  .details img {
    max-width: 100%; 
  }
</style>

<div class="timeline">
  {#each timelineData as event}
    <div class="event">
      <div class="date">{event.date}</div>
      <div class="line"></div> <!-- Vertical line -->
      <div class="details">
        <p>{event.details}</p>
        {#if event.imageUrl}
          <img src={event.imageUrl} alt="Event Image" />
        {/if}
      </div>
    </div>
  {/each}
</div>
