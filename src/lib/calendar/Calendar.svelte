<script lang="ts">
  import { Calendar } from "@fullcalendar/core";
  import dayGridPlugin from "@fullcalendar/daygrid";

  import { db } from "../../config/firestore";
  import { collection, getDocs } from "firebase/firestore";

  const getData = async () => {
    const querySnapshot = await getDocs(collection(db, "appointments"));
    querySnapshot.forEach((doc) => {
      console.log(doc.data());
    });
  };

  getData();

  document.addEventListener("DOMContentLoaded", function () {
    let calendarEl: HTMLElement = document.getElementById("calendar")!;

    let calendar = new Calendar(calendarEl, {
      plugins: [dayGridPlugin],
      // options here
    });

    calendar.render();
  });
</script>

<div id="calendar" />

<style>
</style>
