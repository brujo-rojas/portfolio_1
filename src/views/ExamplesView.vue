<template>
  <div class="examples-container container">
    <h1>Ejemplos</h1>

    <div class="examples">
      <div
        class="card-example-container"
        v-for="(card, index) in cards"
        :key="index"
      >
        <div class="card-example">
          <div class="close" @click.stop="deselectCard()"></div>
          <div class="card-image">
            <img :src="baseUrl + card.image" v-if="card.image" alt="" />
          </div>
          <div class="card-description">
            <span class="title">{{ card.title }}</span>
            <span class="description">{{ card.description }}</span>
            <div class="tags">
              <span class="tag" :key="index" v-for="(tag, index) in card.tags">
                {{ tag }}
              </span>
            </div>
            <div class="card-actions">
              <button
                target="_blank"
                class="outlined"
                @click="openUrl(card.github)"
                v-if="card.github"
              >
                Github
              </button>
              <button
                target="_blank"
                class="outlined"
                @click="openUrl(card.demo)"
                v-if="card.demo"
              >
                DEMO
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from "vue";

export default {
  setup() {
    const amountDots = 20;
    const cards = [
      {
        id: 1,
        title: "Marmota",
        url: "https://marmota-vue.netlify.app/components/table-basic.html",
        image: "/img/ss/marmota.png",
        description: "Extension NPM, Tabla de datos con opciones avanzadas",
        tags: ["npm", "vue", "vuetify"],
        demo: "https://marmota-vue.netlify.app/components/table-example.html",
        github: "https://github.com/brujo-rojas/marmota",
      },
      {
        id: 4,
        title: "Macos JS",
        url: "https://macos-web.netlify.app/",
        image: "/img/ss/macos.png",
        description: "Simulador de MacOs hecho en Javascript y scss",
        tags: ["JS", "CSS 3", "DOM"],
        github: "https://github.com/brujo-rojas/macOsWeb",
        demo: "https://macos-web.netlify.app/",
      },
      {
        id: 3,
        title: "Draw Tools",
        url: "https://drawtool.netlify.app/",
        image: "/img/ss/drawtools.png",
        description:
          "Herramienta web para dibujo clasico, grillas y edicion de img",
        tags: ["Vue 3", "CSS 3", "Canvas", "TS"],
        github: "https://github.com/brujo-rojas/drawtool",
        demo: "https://drawtool.netlify.app/grid",
      },
      {
        id: 5,
        title: "API Mercado de Pociones",
        image: "/img/ss/laravel.jpg",
        description:
          "Demostracion Backend, de api de venta de pociones en Laravel",
        tags: ["REST", "Laravel 9", "MySql"],
        github: "https://github.com/brujo-rojas/potionsmart",
      },
    ];

    let cardSelected = ref(null);
    const baseUrl = window.location.origin;

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
      baseUrl,

      openUrl,
      deselectCard,
    };
  },
};
</script>

<style lang="scss">
#app .examples-container.container {
  margin-top: 2em;
  display: flex;
  flex-direction: column !important;
  align-items: center;
  justify-content: start;

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
      width: 50%;
      max-width: 50%;
      min-width: 350px;
      flex: 1 0 50%;
      aspect-ratio: 16 / 9;
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

      &:not(.card-example-full) {
        &:hover {
          background: rgba(0, 131, 143, 0.3);
          box-shadow: 0 11px 15px -7px rgba(0, 0, 0, 0.2),
            0 24px 38px 3px rgba(0, 0, 0, 0.14),
            0 9px 46px 8px rgba(0, 0, 0, 0.12), 0 0 4px rgba(24, 255, 255, 1) !important;
          transform: scale(1.2);
          z-index: 3;
          border-color: rgba(24, 255, 255, 1);
          .card-description {
            top: 0%;
            background: linear-gradient(
              0deg,
              rgba(0, 0, 0, 1) 0%,
              rgba(0, 0, 0, 0.8) 100%
            );
            backdrop-filter: blur(8px);
          }
        }

        /*&:active {
          background: rgba(0, 131, 143, 0.2);
          box-shadow: 0 7px 8px -4px rgba(0, 0, 0, 0.2),
            0 12px 17px 2px rgba(0, 0, 0, 0.14),
            0 5px 22px 4px rgba(0, 0, 0, 0.12) !important;
          transform: scale(1.03);
          border-color: rgba(24, 255, 255, 0.5);

          transition: 0.2s all ease;
        }
        */
      }

      .card-image {
        width: 100%;
        display: flex;
        justify-content: start;
        align-items: center;
        img {
          width: 100%;
        }
      }

      .card-description {
        position: absolute;
        top: calc(100% - 3.5em);
        left: 0px;
        width: 100%;
        height: 100%;
        padding: 1em;
        display: flex;
        flex-direction: column;
        transition: 0.3s all ease;
        text-shadow: 0px 1px 0px rgba(0, 0, 0, 0.5),
          0px 0px 5px rgba(0, 0, 0, 1);
        background: linear-gradient(
          0deg,
          rgba(0, 0, 0, 1) 0%,
          rgba(0, 0, 0, 0.6) 90%
        );
        backdrop-filter: blur(2px);

        .title {
          font-size: 1.3em;
        }
        .description {
          margin-top: 1em;
        }
        .tag {
          display: inline-block;
          background: rgba(0, 96, 100, 1);
          color: white;
          border-radius: 20px;
          padding: 2px 1em;
          margin: 4px 0.5em;
        }
        .card-actions {
          button.outlined {
            color: white;
            border-radius: 20px;
            border: 1px solid white;
            background: transparent;
            padding: 4px 1em;
            margin: 0.5em;
          }
        }
      }
    }
  }
}
</style>
