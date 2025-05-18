<template>
  <div class="container">
    <!-- 热门歌手 -->
    <GeneralCpn header="热门歌手">
      <template #firstline>
        <div class="artist-list">
          <div class="every-artist" v-for="(item, index) in artist" :key="index">
            <img :src="item.picUrl" alt="item.altUrl" class="artist-img">
            <p class="artist-name">{{ item.name }}</p>
          </div>
        </div>
      </template>
    </GeneralCpn>
    <!-- 榜单 -->
    <GeneralCpn header="榜单">
      <template #firstline>
        <div class="rank-list">
          <div class="song-list" v-for="(item, index) in part2" :key="index">
            <div class="song-item-title">
              <h2>{{ item.name }}</h2>
              <p>{{ item.description }}</p>
            </div>
            <div class="song-item-list">
              <div class="song-item" v-for="(song, index) in item.tracks" :key="index">
                <p>{{ index + 1 }}-{{ song.name }}</p>
              </div>
            </div>
          </div>
        </div>
      </template>
    </GeneralCpn>
  </div>


</template>
<script>
import artist from './data/artist';
import hotSong from './data/hotSong';
import newSong from './data/newSong';
import originSong from './data/originSong';

import GeneralCpn from './components/GeneralCpn.vue';

export default {
  components: {
    GeneralCpn
  },
  data() {
    return {
      artist: artist,
      part2: [newSong, hotSong, originSong]
    }
  }
}


</script>
<style scoped>
.container {
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  gap: 40px;
  padding: 20px 0;
}

/* 热门歌手 */
.artist-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 25px;
  margin-top: 20px;
}

.every-artist {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 10px;
  width: 100px;
}

.artist-img {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.artist-name {
  margin-top: 10px;
  font-size: 14px;
  font-weight: 500;
  color: #333;
  text-align: center;
}

/* 榜单 */
.rank-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 20px;
  width: 100%;
}

.song-list {
  flex: 1;
  min-width: 280px;
  background: #fff;
  border-radius: 12px;
  padding: 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.song-item-title {
  margin-bottom: 15px;
  padding-bottom: 10px;
  border-bottom: 1px solid #f0f0f0;
}

.song-item-title h2 {
  font-size: 18px;
  color: #333;
  margin-bottom: 5px;
}

.song-item-title p {
  font-size: 13px;
  color: #888;
  line-height: 1.4;
}

.song-item-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.song-item {
  padding: 8px 0;
  border-bottom: 1px dashed #f0f0f0;
}

.song-item:last-child {
  border-bottom: none;
}

.song-item p {
  font-size: 14px;
  color: #555;
  margin: 0;
}

.song-item:hover p {
  color: #1db954;
}
</style>