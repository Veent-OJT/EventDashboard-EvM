<script lang="ts">
  import { event } from '$lib/data/eventData';
  import EditEventModal from './EditEventModal/EditEventModal.svelte';
  import { writable } from 'svelte/store';

  const isModalOpen = writable(false);
  let selectedImage: string | null = null;
  let fileInput: HTMLInputElement | null = null;

  function removeImage(event: Event) {
    event.stopPropagation();
    selectedImage = null;
    if (fileInput) {
      fileInput.value = "";
    }
  }

  function handleFileUpload(event: Event) {
    const fileInput = event.target as HTMLInputElement;
    if (fileInput.files && fileInput.files.length > 0) {
      const file = fileInput.files[0];
      selectedImage = URL.createObjectURL(file);
    }
  }
</script>

<div class="event-card">
  <button on:click={() => isModalOpen.set(true)} class="edit-button">
    <span class="text-red-500 font-medium text-sm md:text-base">Edit Event</span>
    <img src="/icons/edit-icon.png" alt="Edit" class="h-6 w-auto md:h-7">
    
  </button>
  <EditEventModal isOpen={isModalOpen} />

  <div class="event-details">
    <img src="/event-photo.png" alt="Event" class="event-image">
    <div class="event-info">
      <h1>{event.title}</h1>
      <div class="space-y-2 text-gray-600">
        <p class="flex items-center space-x-2">
          <img src="/icons/date-icon.png" alt="Calendar">
          <span>{event.date}</span>
        </p>
        <p class="flex items-center space-x-2">
          <img src="/icons/pin-icon.png" alt="Location">
          <span>{event.location}</span>
        </p>
        <p class="flex items-center space-x-2">
          <img src="/icons/Copy-icon.png" alt="Link">
          <a href={event.url} class="text-gray-400 bg-gray-200">{event.url}</a>
        </p>
      </div>
    </div>
  </div>

 </div>