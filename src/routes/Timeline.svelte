<!-- Timeline.svelte -->
<script lang="ts">
  import * as Avatar from "$lib/components/ui/avatar";
  let cards = [
    { 
      date: "Dec 2023",
      eventDetails: [
        {
          image : 'images/timeline/image_1.jpg',
          title: 'No amount of technology can convert a bad story into a good story.'
        },
        {
          image : 'images/timeline/image_2.jpg',
          title: "Most people don't have original ideas. Here is how Sam Altman pushes himself to have unpopular ideas."
        }
      ],
    },
    {  
      date: "Jan 2024",
      eventDetails: [],
      company: 'Duggup',
      logo: 'images/timeline/duggup_logo.jpg',
      position : 'Co-Founder and CEO',
      workType : 'Full-time · Remote',
      location : 'San Francisco Bay Area',
      date : 'Nov 2023',
      major: true
    },
    { 
      date: "Dec 2023",
      eventDetails: [
        {
          image : 'images/timeline/image_3.jpg',
          title: 'No amount of technology can convert a bad story into a good story.'
        },
        {
          image : 'images/timeline/image_4.png',
          title: 'Your biggest regrets at 80 will be acts of omission.'
        },
      ],
    },
    {  
      date: "Jan 2024",
      eventDetails: [],
      company: 'BetterUp',
      position : 'VP Engineering',
      logo : 'images/timeline/betterup_logo.jpg',
      workType : 'Full-time',
      location : 'San Francisco Bay Area',
      date : 'Sep 2022',
      major: true
    },
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
    padding: 0px 120px 60px 120px;
  }

  .event {
    display: flex;
    align-items: normal;
    margin-bottom: 2px;
    height: 250px;
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
    margin-right: 20px;
  }

  .details img {
    max-width: 100%; 
  }
  
  .dot {
    width: 11px;
    height: 10px;
    background-color: white;
    border-radius: 50%;
    border: 3px solid #0066FF;
    margin-right: -9px;
  }
  
  .major-dot {
    width: 12px;
    height: 10px;
    background-color: white;
    border-radius: 50%;
    border: 9px solid #0066FF;
    margin-right: -15px;
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

  .company-details {
    display: flex;
    flex-direction: column;
    font-size: 12px;
    color: #7a9299;
    font-style: inter;
    font-weight: 400;
    width: auto;
  }

  .company-details p{
    margin: 0;
  }

  .event-details {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .event-details p {
    margin: 0;
    font-size: 12px;
    color: #7a9299;
    font-style: inter;
    font-weight: 400;
  }

  .details img{
    border-radius: 50%;
  }

  .position-details {
    display: flex;
    flex-direction: column;
    margin-left: 20px;
  }

  .position-details h2 {
    margin: 0;
    font-style: inter;
    font-weight: 700;
  }
  
  .card-container {
    display: flex;
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
            <img src={event.logo} alt="logo" width="40px" height="40px" />
            {event.company}
            <div class="company-details">
              <p>San Francisco Bay Area</p>
              <p>Joined</p>
              <p>{event.date}</p>
            </div>
          </div> 
          <div class="major-dot"></div>
        {:else}
          <div class="details">
            {event.date}
          </div> 
          <div class="dot"></div>
        {/if}
      </div>
      <div class="details {event.major ? 'event-details' : ''}" >
        {#if event.major}
          <div class="position-details">
            <h2>{event.position}</h2>
            <p>{event.workType}</p>  
          </div>
        {:else}
          <div class="card-container">
            {#each event.eventDetails as image}
              <Card imageUrl={image.image} description={image.title}/>
            {/each}
          </div>
        {/if}
      </div>
    </div>
  {/each}
</div>
