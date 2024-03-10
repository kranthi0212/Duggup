<!-- Timeline.svelte -->
<script>
  // Sample data for the timeline
  let cards = [
    { date: "Dec 2023",imageUrl: 'https://s3-alpha-sig.figma.com/img/ccdc/bd9b/5b2f7dca180260dd9a121e21e4ccb158?Expires=1710720000&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=dOWBi6OHLSab0NnAaNUUXQkXB5~7u0al1jfpXxNgA0tlnAiMVIOqESi-PMhBkg8XTcM3Avu-~kmWy9R46SPhcRdaDFIUnCnnTw-Oi~LymMYl4APflb5NEEJnEIch5ZUw2mtvpnsXPg0AJtbR3wGRzECIOzQVAluoDWOxQDzqiDZPZBgbXQ0iWXyR9ecwlUY4LHEkdZ-ZeDkU3bU39Pw87Vt2Q7QsE9wY2baFiD7KLkYWCuoNm2DF6KoN5KkW6eKcM8C102~UPvSom0~4dxklFMeV6S4ZI3glmKDZVMJXXAcYsGQRYv-z8QtklRtpuE7ZuNM4CeF85M4OW5L8Ob848A__',
    details: 'No amount of technology can convert a bad story into a good story.' },
    {  date: "Jan 2024",imageUrl: 'https://via.placeholder.com/300', details: 'Description of Card 2', major: true },
    {  date: "Jan 2024",imageUrl: 'https://via.placeholder.com/300', details: 'Description of Card 3' }
  ];
    let navLinks = [
        { text: 'Home', iconLink: 'images/nav/home.svg' },
        { text: 'Explore', iconLink: 'images/nav/explore.svg' },
        { text: 'Learn', iconLink: 'images/nav/learn.svg' }
    ];
    import Card from './Card.svelte';
</script>

<style>
  .timeline {
    display: flex;
    flex-direction: column;
    padding : 0px 120px 60px 120px;
    
  }

  .event {
    display: flex;
    align-items: normal;
    margin-bottom: 2px;
  }

  .date {
    width: 180px; 
    font-weight: bold;
    text-align: right;
    border-right: 2px dotted #778fb1;
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
  {#each cards as event}
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
          <Card imageUrl={event.imageUrl} description={event.details} />
      </div>
    </div>
  {/each}
</div>