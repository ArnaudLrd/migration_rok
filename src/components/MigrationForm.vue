<template>
    <div class="flex items-center justify-center min-h-screen bg-gray-100 p-4">
      <div class="w-full max-w-md bg-white shadow-lg rounded-lg overflow-hidden">
        <div class="bg-cover bg-center p-5">
          <h1 class="text-2xl font-bold">Migration Request</h1>
          <p class="mt-2">Kingdom 3135</p>
          <hr class="border-t border-gray-300 mt-5" />
        </div>
        <div class="p-5">
          <form @submit.prevent="submitForm" class="space-y-4">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="space-y-2">
                <label for="discord-pseudo" class="font-semibold">Discord Pseudo</label>
                <input v-model="form.discordPseudo" id="discord-pseudo" type="text" placeholder="Enter your Discord name" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required />
              </div>
              <div class="space-y-2">
                <label for="account-id" class="font-semibold">Account ID</label>
                <input v-model="form.accountID" id="account-id" type="text" placeholder="Enter your Account ID" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required />
              </div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="space-y-2">
                <label for="power" class="font-semibold">Power</label>
                <input v-model="form.power" id="power" type="number" placeholder="Enter your Power" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required />
              </div>
              <div class="space-y-2">
                <label for="kill-points" class="font-semibold">Kill Points</label>
                <input v-model="form.killPoints" id="kill-points" type="number" placeholder="Enter your Kill Points" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required />
              </div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="space-y-2">
                <label for="dead-troops" class="font-semibold">Dead Troops</label>
                <input v-model="form.deadTroops" id="dead-troops" type="number" placeholder="Enter your Dead Troops" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required />
              </div>
              <div class="space-y-2">
                <label for="match-tech" class="font-semibold">Max Tech</label>
                <select v-model="form.matchTech" id="match-tech" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required>
                  <option value="" disabled>Select an option</option>
                  <option value="yes">Yes</option>
                  <option value="no">No</option>
                </select>
              </div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="space-y-2">
                <label for="garrison-rally-none" class="font-semibold">Account type</label>
                <select v-model="form.garrisonRallyNone" id="garrison-rally-none" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required>
                  <option value="" disabled>Select an option</option>
                  <option value="garrison">Garrison</option>
                  <option value="rally">Rally</option>
                  <option value="none">None</option>
                </select>
              </div>
              <div class="space-y-2">
                <label for="vip" class="font-semibold">VIP</label>
                <input v-model="form.vip" id="vip" type="number" placeholder="Enter your VIP level" class="block w-full border border-gray-300 rounded-md shadow-sm p-2" required />
              </div>
            </div>
            <div class="py-4 relative">
              <button type="submit" class="w-full bg-[#8c7853] text-white hover:bg-[#6b5e41] transition-colors py-2 px-4 rounded-md shadow-sm" :disabled="isSubmitting">
                <span v-if="!isSubmitting">Submit Migration Request</span>
                <span v-else class="flex justify-center items-center">
                  <svg class="animate-spin h-5 w-5 text-white mr-2" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4z"></path>
                  </svg>
                  Submitting...
                </span>
              </button>
            </div>
          </form>
          <p v-if="responseMessage" class="mt-4">{{ responseMessage }}</p>
        </div>
      </div>
    </div>
  </template>
    
  <script>
  export default {
    data() {
      return {
        form: {
          discordPseudo: '',
          accountID: '',
          power: '',
          killPoints: '',
          deadTroops: '',
          matchTech: '',
          garrisonRallyNone: '',
          vip: ''
        },
        responseMessage: '',
        isSubmitting: false
      }
    },
    methods: {
      submitForm() {
        this.isSubmitting = true;
        const formData = new FormData();
        for (const key in this.form) {
          formData.append(key, this.form[key]);
        }
        formData.append('Status', 'Pending');
    
        fetch('https://script.google.com/macros/s/AKfycbyX-bUvdoGph19gMKFzLGhyLwUsMASnU0LhsJ4ZoD43B4VntLCbiOn9syH37Arf_uzPTg/exec', {
          method: 'POST',
          mode: 'no-cors',
          body: formData
        })
        .then(() => {
          this.responseMessage = 'Response submitted successfully.';
          this.resetForm();
          this.isSubmitting = false;
        })
        .catch(() => {
          this.responseMessage = 'Error submitting response.';
          this.isSubmitting = false;
        });
      },
      resetForm() {
        this.form = {
          discordPseudo: '',
          accountID: '',
          power: '',
          killPoints: '',
          deadTroops: '',
          matchTech: '',
          garrisonRallyNone: '',
          vip: ''
        };
      }
    }
  }
  </script>
  
  <style>
  .animate-spin {
    animation: spin 1s linear infinite;
  }
  
  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }
  </style>
  