<template>
  <v-container
    class="fill-height d-flex flex-column justify-start bg-grey px-0 pt-0"
  >
    <div
      v-for="{
        id,
        title,
        author,
        date,
        article,
        imgs,
        tags,
        nice,
        collect,
        commet,
        watch,
      } in articleList"
      :key="id"
      class="article_block"
    >
      <p class="font-weight-bold">{{ title }}</p>
      <div class="main">
        <div class="text_block">
          <p>
            {{ author }} <span>{{ date }}</span>
          </p>
          <p>{{ article }}</p>
        </div>
        <div class="img_block" :class="{ single_img: imgs.length === 1 }">
          <img v-for="img in imgs" :key="img" :src="img" />
        </div>
      </div>

      <div class="d-flex align-center mt-2 overflow-hidden">
        <div class="tag_wrap d-flex flex-shrink-1">
          <div v-for="tag in tags" :key="tag" class="tag mr-1">
            {{ tag }}
          </div>
        </div>
        <p class="remark">
          {{ `點讚 ${nice} 收藏 ${collect} 評論 ${commet} 觀看 ${watch}` }}
        </p>
      </div>
    </div>
  </v-container>
</template>

<script setup>
import { shallowReactive } from "vue";

const articleList = shallowReactive([
  {
    id: 1,
    title: "我好像為甚麼事情很悲哀。我想起生命",
    author: "張杰攻",
    date: "2021.09.12",
    article:
      "內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文",
    imgs: ["http://placehold.it/250x150"],
    tags: ["美文", "故事", "精選優質"],
    nice: 231,
    collect: 34,
    commet: 34,
    watch: 786,
  },

  {
    id: 2,
    title: "我好像為甚麼事情很悲哀。我想起生命",
    author: "張杰攻",
    date: "2021.09.12",
    article:
      "內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文",
    imgs: ["http://placehold.it/250x150", "http://placehold.it/250x150"],
    tags: ["美文", "故事", "美文", "故事", '故事'],
    nice: 231,
    collect: 34,
    commet: 34,
    watch: 786,
  },
  {
    id: 3,
    title: "我好像為甚麼事情很悲哀。我想起生命",
    author: "張杰攻",
    date: "2021.09.12",
    article:
      "內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文內文",
    imgs: [
      "http://placehold.it/250x150",
      "http://placehold.it/250x150",
      "http://placehold.it/250x150",
    ],
    tags: ["美文", "故事"],
    nice: 231,
    collect: 34,
    commet: 34,
    watch: 786,
  },
]);
//
</script>

<style lang="scss" scoped>
.article_block {
  background-color: white;
  color: black;
  padding: 0.6rem;

  &:not(:first-of-type) {
    margin-top: 0.6rem;
  }
  .main {
    display: flex;
    flex-wrap: wrap;

    .text_block {
      flex: 1 1 70%;
    }

    .img_block {
      display: flex;
      max-height: 120px;
      width: 100%;
      &.single_img {
        width: 30%;
      }
      > img {
        width: 100%;
        flex: 1 1 auto;
        object-fit: contain;
        overflow: hidden;

        &:not(:first-of-type) {
          margin-left: 0.4rem;
        }
      }
    }
  }

  .tag_wrap {
    display: flex;
    flex: 1 1 auto;
    overflow: hidden;
    flex-wrap: wrap;
    .tag {
      font-size: 12px;
      white-space: nowrap;
      background-color: grey;
      height: fit-content;
      color: white;
      padding: 0.2rem;
      flex-shrink: 1;
      flex-wrap: wrap;

      &:not(:last-of-type) {
        margin-inline-end: 0.4rem;
      }
    }
  }

  .remark {
    font-size: 14px;
    color: #aaa;
    white-space: nowrap;
  }
}
</style>