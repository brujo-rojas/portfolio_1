<template>
  <div class="examples-container container container-full">
    <h1>Ejemplos</h1>

    <div class="examples">
      <div
        class="card-example-container"
        v-for="(card, index) in cards"
        :key="index"
      >
        <div @click="card.url && openUrl(card.url)" class="card-example">
          <div class="close" @click.stop="deselectCard()"></div>
          <div class="card-image"></div>
          <div class="card-description">
            <span class="title">{{ card.title }}</span>
            <span class="description">{{ card.description }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { ref, computed } from "vue";

export default {
  setup() {
    const amountDots = 20;
    const cards = [
      {
        id: 1,
        title: "Marmota",
        url: "https://marmota-vue.netlify.app/components/table-basic.html",
        description: "a Description lorem lorem lorem lorem",
      },
      {
        id: 2,
        title: "Youtube Collection",
        url: "https://yt-collection.netlify.app/videos",
        description: "a Description lorem lorem lorem lorem",
      },
      {
        id: 3,
        title: "Draw Tools",
        url: "https://drawtool.netlify.app/",
        description: "a Description lorem lorem lorem lorem",
      },
      {
        id: 4,
        title: "Macos JS",
        url: "https://macos-web.netlify.app/",
        description: "a Description lorem lorem lorem lorem",
      },
      {
        id: 5,
        title: "a title 5",
        description: "a Description lorem lorem lorem lorem",
      },
      {
        id: 6,
        title: "a title 6",
        description: "a Description lorem lorem lorem lorem",
      },
    ];

    let cardSelected = ref(null);

    function openUrl(url: string) {
      if (url && window) {
        let res = window.open(url, "_blank");
        if (res) {
          res.focus();
        }
      }
    }

    function deselectCard() {
      cardSelected.value = null;
    }
    return {
      amountDots,
      cards,
      cardSelected,
      openUrl,
      deselectCard,
    };
  },
};
</script>

<style lang="scss">
.examples-container {
  margin-top: 2em;
  display: flex;
  flex-direction: column !important;

  h1 {
    font-size: 4em;
    text-align: left;
    margin-left: 0.3em;
  }

  .examples {
    padding: 3em;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 2em;

    .card-example-container {
      width: 30%;
      max-width: 30%;
      min-width: 250px;
      flex: 1 1 30%;
      height: 300px;
      display: flex;
      flex-direction: row;
    }
    .card-example {
      border-radius: 5px;
      margin: 1em;
      height: calc(100% - 2em);
      width: calc(100% - 2em);
      flex: 1 0 auto;
      box-shadow: 0 3px 5px -1px rgba(0, 0, 0, 0.2),
        0 6px 10px 0 rgba(0, 0, 0, 0.14), 0 1px 18px 0 rgba(0, 0, 0, 0.12) !important;
      transition: 0.4s all ease;
      background-color: rgba(38, 50, 56, 1);
      border: 1px solid transparent;
      display: flex;
      position: relative;
      flex-direction: column;
      overflow: hidden;
      cursor: pointer;

      &:not(.card-example-full) {
        &:hover {
          background: rgba(0, 131, 143, 0.3);
          box-shadow: 0 11px 15px -7px rgba(0, 0, 0, 0.2),
            0 24px 38px 3px rgba(0, 0, 0, 0.14),
            0 9px 46px 8px rgba(0, 0, 0, 0.12), 0 0 4px rgba(24, 255, 255, 1) !important;
          transform: scale(1.05);
          border-color: rgba(24, 255, 255, 1);
          .card-description {
            top: 50%;
          }
        }

        &:active {
          background: rgba(0, 131, 143, 0.2);
          box-shadow: 0 7px 8px -4px rgba(0, 0, 0, 0.2),
            0 12px 17px 2px rgba(0, 0, 0, 0.14),
            0 5px 22px 4px rgba(0, 0, 0, 0.12) !important;
          transform: scale(1.03);
          border-color: rgba(24, 255, 255, 0.5);

          transition: 0.2s all ease;
        }
      }

      .card-image {
        background: green;
        width: 100%;
      }

      .card-description {
        position: absolute;
        top: calc(100% - 3.5em);
        left: 0px;
        width: 100%;
        height: 50%;
        padding: 1em;
        display: flex;
        flex-direction: column;
        transition: 0.3s all ease;
        background: linear-gradient(
          0deg,
          rgba(0, 0, 0, 0.5) 0%,
          rgba(0, 0, 0, 0) 90%
        );

        .title {
          font-size: 1.3em;
        }
        .description {
          margin-top: 1em;
        }
      }
    }
  }
}
</style>
