<script lang="ts">
  export let navigateTo: (path: string) => void;
</script>

<div class=" flex flex-wrap gap-2 mb-6 ml-0 md:ml-6">
  {#each ['Registrants', 'Posts', 'Form', 'Merchant', 'Emails', 'Staff'] as tab}
    <button
      on:click={() => navigateTo('')}
      class="flex-grow md:flex-grow-0 px-4 md:px-6 py-2 rounded-lg font-medium transition-colors text-sm md:text-base {tab === 'Staff' ? 'bg-red-500 text-white' : 'border border-gray-300 text-gray-700 hover:bg-red-500 hover:text-white'}"
    >
      {tab}
    </button>
  {/each}
  
</div>

  <div class="header fixed top-0 left-0 right-0 bg-white">
    <div class="container mx-auto px-4">
      <div class="flex justify-between items-center">
        <!-- Left Section -->
        <div class="flex items-center space-x-4 md:space-x-8">
          <img src="/logo/Veent-red-logo.png" alt="Veent Logo" class="h-5 w-8 md:h-6 md:w-10 cursor-pointer">
          <nav class="nav-links">
            <a href="#" class="nav-link text-red-500">
              <img src="/icons/home-icon.png" alt="Home Icon" class="h-4 w-4 md:h-5 md:w-5">
              <span class="hidden md:inline">Home</span>
            </a>
            <a href="#" class="nav-link text-gray-600">
              <img src="/icons/wallet-icon.png" alt="Wallet Icon" class="h-4 w-4 md:h-5 md:w-5">
              <span class="hidden md:inline">Wallet</span>
            </a>
          </nav>
        </div>

        <!-- Right Section -->
        <div class="flex items-center space-x-2 md:space-x-4">
          <button class="p-1 md:p-2 hover:bg-gray-100 rounded-full">
            <img src="/icons/search-icon.png" alt="Search Icon" class="h-3 w-3 md:h-4 md:w-4 cursor-pointer">
          </button>
          <button class="p-1 md:p-2 hover:bg-gray-100 rounded-full">
            <img src="/icons/notification-icon.png" alt="Notification-Icon" class="h-3 w-3 md:h-4 md:w-4 cursor-pointer">
          </button>
          <img src="/Group 9968.png" alt="Profile-Icon" class="h-5 w-5 md:h-6 md:w-6 cursor-pointer">
        </div>
      </div>
    </div>
  </div>