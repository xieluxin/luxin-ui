<template>
  <div>
    <div class="topNavAndBanner">
      <TopNav/>
      <div class="banner">
        <h1>luxin</h1>
        <h2>基于 Vue 3，面向开发者的组件库</h2>
        <p class="actions">
          <router-link to="/doc">查看详情</router-link>
        </p>
      </div>
    </div>
    <div class="luXin-items">
      <div class="luXin-item">
        <div class="box">
          <img src="../../src/assets/img.png" alt="">
          <div class="info">
            <p>个人项目</p>
            <h4>luXin博客</h4>
            <p>vue2+SpringBoot实现前后端分离项目</p>
            <a class="more" href="">了解更多 ></a>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script lang="ts">
import TopNav from '../components/common/TopNav.vue';

export default {
  components: {TopNav},
};
</script>


<style lang='scss' scoped>
$green: #02bcb0;
$border-radius: 4px;
$wordColor: #007974;
.topNavAndBanner {
  background: linear-gradient(145deg, rgba(227, 255, 253, 1) 0%, rgba(183, 233, 230, 1) 100%);
  clip-path: ellipse(80% 60% at 50% 40%); // 实现圆弧效果
}

.banner {
  color: $wordColor;
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  > .actions {
    padding: 8px 0;

    a {
      margin: 0 8px;
      background: $green;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: 32px;

      &:hover {
        text-decoration: none;
      }
    }
  }
}

.luXin-items {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;

  .luXin-item {
    .box {
      position: relative;
      border-radius: 6px ;
      width: 446px;
      height: 314px;
      overflow: hidden;
      box-shadow: rgb(240, 241, 242) 0px 2px 8px;
      img {
        width: 100%;
        height: 100%;
        transition: all .4s;
      }
    }

    .box:hover img {
      transform: scale(1.05);
    }

    .box::after {
      content: '';
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-image: linear-gradient(rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.5));
      opacity: 0;
      z-index: 1;
    }

    .box:hover::after {
      opacity: 1;
    }

    .info {
      position: absolute;
      left: 0;
      bottom: -50px;
      z-index: 999;
      padding: 25px 30px;
      font-size: 18px;
      color: #ffffff;
      transition: all .5s;

      h4 {
        font-size: 24px;
        margin: 5px 0;
      }

      .a {
        color: #ffffff;
        margin-top: 15px;
        display: block;
      }

      .more {
        margin-top: 15px;
      }
    }

    .box:hover .info {
      bottom: 0;
    }
  }
}

.features {
  margin: 64px auto;
  padding: 0 16px;
  @media (min-width: 800px) {
    width: 800px;
    > ul {
      > li {
        width: 50%;
      }
    }
  }
  @media (min-width: 1200px) {
    width: 1200px;
    > ul {
      > li {
        width: 33.3333%;
      }
    }
  }

  > ul {
    display: flex;
    flex-wrap: wrap;

    > li {
      margin: 16px 0;
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 80px auto;
      grid-template-rows: 1fr auto;

      > svg {
        grid-area: icon;
        width: 64px;
        height: 64px;
      }

      > h3 {
        grid-area: title;
        font-size: 28px;
      }

      > p {
        grid-area: text
      }
    }
  }
}
</style>
