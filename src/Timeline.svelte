<!-- Timeline.svelte -->
<script>
  // Sample data for the timeline
  let timelineData = [
    { date: "Dec 2023", details: "Event details here...", imageUrl: "event1.jpg" },
    { date: "Jan 2024", details: "Event details here...", imageUrl: "event2.jpg" },
    { date: "Feb 2024", details: "Event details here...", imageUrl: "event3.jpg" , major: true}
  ];
</script>

<style>
  .timeline {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }

  .event {
    display: flex;
    align-items: flex-start;
    margin-bottom: 2px;
    height: 100px;
  }

  .date {
    width: 200px; 
    font-weight: bold;
    text-align: right;
    border-right: 2px dotted #778fb1;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    position: relative;
  }

  .details {
    margin-left: 30px; 
    padding-left: 20px; 
  }

  .details img {
    max-width: 100%; 
  }
  .dot {
    width: 10px;
    height: 10px;
    background-color: white;
    border-radius: 50%;
    border: 3px solid #0066FF;
    margin-right: -9px;
  }
  .major-dot {
    width: 10px;
    height: 10px;
    background-color: white;
    border-radius: 50%;
    border: 9px solid #0066FF;
    margin-right: -15px;
  }
  .date .details {
    padding-right: 20px;
  }
  .arrow {
    position: absolute;
    top: 0;
    margin-right: -7px;
    padding: 5px !important;
    border: 5px solid #778fb1;
	  border-width: 0 2px 2px 0;
    z-index: 1;
    margin-top: -6px;
  }
  .major-event {
    margin-top: 8px;
  }
</style>

<div class="timeline">
  {#each timelineData as event}
    <div class="event {event.major ? 'major-event' : ''}">
      <div class="date">
        {#if event.major}
        <div class="arrow up"></div>
        <div class="details">
          {event.date}
        </div> 
          <div class="major-dot">
          </div>
        {:else}

        <div class="details">
          {event.date}
        </div> 
          <div class="dot">
          </div>
        {/if}
      </div>
      <div class="details">
        <p>{event.details}</p>
        {#if event.imageUrl}
          <img src={event.imageUrl} alt="Event Image" />
        {/if}
      </div>
    </div>
  {/each}
</div>
