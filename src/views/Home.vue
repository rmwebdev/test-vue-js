<template>
  <div class="home relative">
    <div class="logos text-center">
      <img src="../assets/logo.svg" class="logos__image">
    </div>
    <div class="text-center group__input">
      <div class="button__group">
        <v-btn class="mx-2" text color="primary">
          Artist
        </v-btn>
        /

        <v-btn class="mx-2" text color="primary">
          Album
        </v-btn>
        /
        <v-btn class="mx-2" text color="primary">
          Title
        </v-btn>
      </div>
      <div class="search__group mb-2">
        <form v-on:submit.prevent="onSearch">
          <input type="text" v-model="search" class="searchTerm" placeholder="Search" />
        </form>
      </div>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
  },
  data: () => ({
    items: [
      {
        icon: 'mdi-wifi',
        text: 'Wifi',
      },
      {
        icon: 'mdi-bluetooth',
        text: 'Bluetooth',
      },
      {
        icon: 'mdi-chart-donut',
        text: 'Data Usage',
      },
    ],
    search: '',
  }),
  methods: {
    onSearch() {
      console.log(this.search)
      if (this.search) {
        this.$router.push({
          name: 'SongList',
          params: { name: this.search }
        });
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  background-image: linear-gradient(180deg, #712bda, #a45deb);
}

.logos {
  height: 50%;
  position: relative;
}

.logos__image {
  position: absolute;
  bottom: 0;

  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
}

.form-control {
  width: 80%;
}


.mx-2 {
  padding: 20px;
}


.title-search {
  position: absolute;
  left: 0;
  right: 0;
  top: 40%;
  margin-left: auto;
  margin-right: auto;
  width: 100px;
  color: white;
}

.group__input {
  position: absolute;
  left: 0;
  right: 0;

  margin-left: auto;
  margin-right: auto;
  top: 60%;
  width: 90%
}

.button__group {
  background-color: white;
  border-radius: 20px;
  padding: 10px;
  line-height: 40px;
  margin-bottom: 10px;
}

.search__group {
  background-color: white;
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.2);
  ;
  padding: 10px;
  line-height: 40px;
  line-height: 40px;
}

.searchTerm {
  width: 90%;
  color: #fff;
  outline-color: #cccccc;
  padding-left: 10px;
}
</style>
