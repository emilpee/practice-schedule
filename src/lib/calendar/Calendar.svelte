<script lang="ts">
    import { Calendar } from '@fullcalendar/core';
import dayGridPlugin from '@fullcalendar/daygrid';

document.addEventListener('DOMContentLoaded', function() {
  let calendarEl: HTMLElement = document.getElementById('calendar')!;

  let calendar = new Calendar(calendarEl, {
    plugins: [ dayGridPlugin ]
    // options here
  });

  calendar.render();
});
</script>

<style>
    /* your styles go here */
</style>

<!-- markup (zero or more items) goes here --> 

<div id="calendar"></div>