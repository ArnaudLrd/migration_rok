<template>
  <div class="flex items-center justify-center min-h-screen bg-gradient-to-b from-amber-800 to-amber-950 p-4">
    <div class="w-full max-w-lg bg-amber-50 shadow-2xl rounded-lg overflow-hidden border-2 border-amber-600 transform transition-all duration-500 hover:scale-[1.01]">
      <!-- Header with RoK themed styling -->
      <div class="bg-gradient-to-r from-amber-700 to-amber-900 p-6 relative overflow-hidden">
        <div class="absolute top-0 left-0 w-full h-full opacity-20">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" class="w-full h-full">
            <path d="M25,30 L50,10 L75,30 L75,70 L50,90 L25,70 Z" fill="none" stroke="white" stroke-width="0.5"></path>
            <path d="M35,40 L50,30 L65,40 L65,60 L50,70 L35,60 Z" fill="none" stroke="white" stroke-width="0.5"></path>
          </svg>
        </div>
        <h1 class="text-3xl font-bold text-amber-100 relative z-10 flex items-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 mr-2 text-yellow-400" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M10 2a1 1 0 011 1v1.323l3.954 1.582a1 1 0 01.646.928V12.5a1 1 0 01-.5.866l-4 2.5a1 1 0 01-1 0l-4-2.5a1 1 0 01-.5-.866V6.833a1 1 0 01.646-.928L10 3.323V3a1 1 0 011-1z" clip-rule="evenodd" />
          </svg>
          Migration Request
        </h1>
        <p class="mt-2 text-amber-200 flex items-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
          </svg>
          Kingdom 3568
        </p>
        <div class="w-full h-1 bg-gradient-to-r from-yellow-400 via-amber-500 to-yellow-400 mt-5"></div>
      </div>

      <!-- Form Content -->
      <div class="p-6">
        <form @submit.prevent="submitForm" class="space-y-6">
          <!-- Discord & Account ID -->
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="discord-pseudo" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" />
                </svg>
                Discord Pseudo
              </label>
              <input 
                v-model="form.discordPseudo" 
                id="discord-pseudo" 
                type="text" 
                placeholder="Enter your Discord name" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required 
              />
            </div>
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="account-id" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd" />
                </svg>
                Account ID
              </label>
              <input 
                v-model="form.accountID" 
                id="account-id" 
                type="text" 
                placeholder="Enter your Account ID" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required 
              />
            </div>
          </div>

          <!-- Power & Kill Points -->
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="power" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M12.395 2.553a1 1 0 00-1.45-.385c-.345.23-.614.558-.822.88-.214.33-.403.713-.57 1.116-.334.804-.614 1.768-.84 2.734a31.365 31.365 0 00-.613 3.58 2.64 2.64 0 01-.945-1.067c-.328-.68-.398-1.534-.398-2.654A1 1 0 005.05 6.05 6.981 6.981 0 003 11a7 7 0 1011.95-4.95c-.592-.591-.98-.985-1.348-1.467-.363-.476-.724-1.063-1.207-2.03zM12.12 15.12A3 3 0 017 13s.879.5 2.5.5c0-1 .5-4 1.25-4.5.5 1 .786 1.293 1.371 1.879A2.99 2.99 0 0113 13a2.99 2.99 0 01-.879 2.121z" clip-rule="evenodd" />
                </svg>
                Power
              </label>
              <input 
                v-model="form.power" 
                id="power" 
                type="number" 
                placeholder="Enter your Power" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required 
              />
            </div>
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="kill-points" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM7 9a1 1 0 100-2 1 1 0 000 2zm7-1a1 1 0 11-2 0 1 1 0 012 0zm-.464 5.535a1 1 0 10-1.415-1.414 3 3 0 01-4.242 0 1 1 0 00-1.415 1.414 5 5 0 007.072 0z" clip-rule="evenodd" />
                </svg>
                Kill Points
              </label>
              <input 
                v-model="form.killPoints" 
                id="kill-points" 
                type="number" 
                placeholder="Enter your Kill Points" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required 
              />
            </div>
          </div>

          <!-- Dead Troops & Max Tech -->
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="dead-troops" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M10 1.944A11.954 11.954 0 012.166 5C2.056 5.649 2 6.319 2 7c0 5.225 3.34 9.67 8 11.317C14.66 16.67 18 12.225 18 7c0-.682-.057-1.35-.166-2.001A11.954 11.954 0 0110 1.944zM11 14a1 1 0 11-2 0 1 1 0 012 0zm0-7a1 1 0 10-2 0v3a1 1 0 102 0V7z" clip-rule="evenodd" />
                </svg>
                Dead Troops
              </label>
              <input 
                v-model="form.deadTroops" 
                id="dead-troops" 
                type="number" 
                placeholder="Enter your Dead Troops" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required 
              />
            </div>
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="match-tech" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M11.3 1.046A1 1 0 0112 2v5h4a1 1 0 01.82 1.573l-7 10A1 1 0 018 18v-5H4a1 1 0 01-.82-1.573l7-10a1 1 0 011.12-.38z" clip-rule="evenodd" />
                </svg>
                Max Tech
              </label>
              <select 
                v-model="form.matchTech" 
                id="match-tech" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required
              >
                <option value="" disabled>Select an option</option>
                <option value="yes">Yes</option>
                <option value="no">No</option>
              </select>
            </div>
          </div>

          <!-- Account Type & VIP -->
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="garrison-rally-none" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path d="M3 12v3c0 1.657 3.134 3 7 3s7-1.343 7-3v-3c0 1.657-3.134 3-7 3s-7-1.343-7-3z" />
                  <path d="M3 7v3c0 1.657 3.134 3 7 3s7-1.343 7-3V7c0 1.657-3.134 3-7 3S3 8.657 3 7z" />
                  <path d="M17 5c0 1.657-3.134 3-7 3S3 6.657 3 5s3.134-3 7-3 7 1.343 7 3z" />
                </svg>
                Account Type
              </label>
              <select 
                v-model="form.garrisonRallyNone" 
                id="garrison-rally-none" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required
              >
                <option value="" disabled>Select an option</option>
                <option value="garrison">Garrison</option>
                <option value="rally">Rally</option>
                <option value="none">None</option>
              </select>
            </div>
            <div class="space-y-2 transition-all duration-300 transform hover:translate-y-[-2px]">
              <label for="vip" class="font-semibold text-amber-900 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-1 text-amber-700" viewBox="0 0 20 20" fill="currentColor">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>
                VIP Level
              </label>
              <input 
                v-model="form.vip" 
                id="vip" 
                type="number" 
                placeholder="Enter your VIP level" 
                class="block w-full border-2 border-amber-300 rounded-md shadow-sm p-2 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 transition-all duration-300 bg-amber-50" 
                required 
              />
            </div>
          </div>

          <!-- Submit Button -->
          <div class="py-4 relative">
            <button 
              type="submit" 
              class="w-full bg-gradient-to-r from-amber-700 to-amber-900 text-white hover:from-amber-600 hover:to-amber-800 transition-all duration-300 py-3 px-4 rounded-md shadow-lg border border-amber-600 transform hover:translate-y-[-2px] focus:outline-none focus:ring-2 focus:ring-amber-500 focus:ring-opacity-50"
              :disabled="isSubmitting"
            >
              <span v-if="!isSubmitting" class="flex justify-center items-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                Submit Migration Request
              </span>
              <span v-else class="flex justify-center items-center">
                <svg class="animate-spin h-5 w-5 text-white mr-2" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                  <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                  <path class="opacity-75" fill="currentColor" d="M4.93 19.07A9.96 9.96 0 0112 22c5.51 0 10-4.49 10-10S17.51 2 12 2 2 6.49 2 12a9.96 9.96 0 012.93 7.07z"></path>
                </svg>
                Processing Request...
              </span>
            </button>
          </div>
        </form>

        <!-- Response Message with animation -->
        <transition name="fade">
          <div v-if="responseMessage" class="mt-4 p-3 rounded-lg" :class="responseStatus === 'success' ? 'bg-green-100 text-green-800 border border-green-200' : 'bg-red-100 text-red-800 border border-red-200'">
            <div class="flex items-center">
              <svg v-if="responseStatus === 'success'" xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2 text-green-600" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2 text-red-600" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7 4a1 1 0 11-2 0 1 1 0 012 0zm-1-9a1 1 0 00-1 1v4a1 1 0 102 0V6a1 1 0 00-1-1z" clip-rule="evenodd" />
              </svg>
              {{ responseMessage }}
            </div>
          </div>
        </transition>
      </div>

      <!-- Footer with RoK themed styling -->
      <div class="bg-gradient-to-r from-amber-800 to-amber-950 p-3 text-center">
        <p class="text-amber-200 text-sm">&copy; {{ new Date().getFullYear() }} Kingdom 3568 | Rise of Kingdoms</p>
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
      responseStatus: '',
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
  
      fetch('https://script.google.com/macros/s/AKfycbzJlmf-BpRYnLaiDeFeB7lPpYEFiVunG3dFXGKpcZU0p0Z323cB_hqwzJk7bMBJym3apQ/exec', {
        method: 'POST',
        mode: 'no-cors',
        body: formData
      })
      .then(() => {
        this.responseMessage = 'Migration request submitted successfully!';
        this.responseStatus = 'success';
        this.resetForm();
        this.isSubmitting = false;
        
        // Auto-hide the message after 5 seconds
        setTimeout(() => {
          this.responseMessage = '';
        }, 5000);
      })
      .catch(() => {
        this.responseMessage = 'Error submitting request. Please try again.';
        this.responseStatus = 'error';
        this.isSubmitting = false;
        
        // Auto-hide the message after 5 seconds
        setTimeout(() => {
          this.responseMessage = '';
        }, 5000);
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

<style scoped>
/* Animations */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s, transform 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* Custom Rise of Kingdoms inspired spinner animation */
.animate-spin {
  animation: spin 1.2s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

/* Input focus animations */
input:focus, select:focus {
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { box-shadow: 0 0 0 0 rgba(217, 119, 6, 0.4); }
  70% { box-shadow: 0 0 0 5px rgba(217, 119, 6, 0); }
  100% { box-shadow: 0 0 0 0 rgba(217, 119, 6, 0); }
}

/* Hover effects for form elements */
input:hover, select:hover {
  border-color: #b45309;
}
</style>