<script setup lang="ts">

const links = {
  0: {
    name: "GitHub",
    link: "https://github.com/christophhehl",
    picture: "images/github.png",
  },
  1: {
    name: "Steam",
    link: "https://steamcommunity.com/id/Skrik36/",
    picture: "images/steam.png",
  },
  2: {
    name: "Spotify",
    link: "https://open.spotify.com/user/conbuilder363",
    picture: "images/spotify.png",
  },
  3: {
    name: "Last.fm",
    link: "https://www.last.fm/user/Skrik_Christoph",
    picture: "images/lastfm.png",
  },
  4: {
    name: "Discord",
    link: "",
    picture: "images/discord.png",
  }
}

function copyDiscordName() {
  const discordName = "skrik"
  navigator.clipboard.writeText(discordName);
  alert("Username copied to clipboard: " + discordName);
}
</script>

<template>
  <div class="background padding_10">
    <div class="container text-center text-white bg-dark rounded" style="--bs-bg-opacity: 0.7;">
      <div class="row">
        <div class="col d-flex justify-content-center align-items-center name padding_10">
          CHRISTOPH HEHL
        </div>
        <div class="col d-flex m-auto justify-content-center flex-wrap">
          <div v-for="i of links" :key="i.name">
            <img v-if="i.name === 'Discord'" :src="i.picture" :alt="i.name" class="logo" @click="copyDiscordName()"
                 style="cursor: pointer">
            <a v-else :href="i.link" class="text-decoration-none">
              <img :src="i.picture" :alt="i.name" class="logo">
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.background {
  height: 100vh;
  background-image: url('../assets/background.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
}

.padding_10 {
  padding: 10vh;
}

.name {
  font-family: 'Montserrat', sans-serif;
  font-size: 3vw;
}

.logo {
  height: 3.5rem;
  width: auto;
  margin: 1rem;
}
</style>