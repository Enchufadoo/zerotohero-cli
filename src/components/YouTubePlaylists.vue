<template>
  <div class="youtube-playlists">
    <div
      v-for="playlist of playlists"
      class="youtube-playlist media rounded shadow"
    >
      <a :href="`#/${$l1.code}/${$l2.code}/youtube/playlist/${playlist.id}`" class="playlist-link">
        <div class="youtube-thumbnail-wrapper aspect-wrapper">
          <img :src="playlist.thumbnail" class="youtube-thumbnail aspect" />
        </div>
        <div class="media-body">
          <div class="playlist-title">{{ playlist.title }}</div>
          <div class="playlist-description">
            {{ playlist.count }} video{{ playlist.count > 1 ? 's' : '' }}
          </div>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    playlists: {
      type: Array
    }
  }
}
</script>

<style lang="scss">
.youtube-playlists {
  display: flex;
  flex-wrap: wrap;
}
.youtube-playlist {
  min-width: 15rem;
  flex: 1;
  margin: 1rem;
}
a.playlist-link,
a.playlist-link:hover {
  color: #666;
  text-decoration: none;
  .playlist-title {
    font-weight: bold;
  }
  .playlist-description {
    color: #999;
    text-decoration: none;
  }
}
</style>
