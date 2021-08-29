<template>
   <div class="conatiner">
      <h2>Я найду тебя!</h2>
      <input 
         type="text" 
         name="text"
         placeholder="Искать"
         @input="searchText = $event.target.value"
      >
      <h5>Всего имен: {{ users.length }}, совпадений: {{ getFilteredName.length }}</h5>
      <p
         v-for="(user, index) in getFilteredName"
         :key="index"
      >
         {{ user }}
      </p>
  </div>

</template>

<script>
export default {
   name: 'FilteredUsers',
   data() {
      return {
         searchText: '',
         users: ['Расул', 'Самат', 'Еркебулан', 'Сабит', 'Нуржан'],
      }
   },

   computed: {
      getFilteredName() {
         return this.users.filter(user => user.toLowerCase().includes(this.searchText.toLowerCase()))
      }
   }

   //watch: {
   //   currentPage(page) {
   //      this.loadUsers(page)
   //   }
   //}

}
</script>

<style src="@/assets/styles/main.css">



</style>