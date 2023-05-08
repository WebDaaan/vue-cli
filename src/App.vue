<template>
  <div class="content">
    <div class="content-inf">
      <div class="inf-up inf-teg">
        <h1>{{ up }} </h1>
        <p>За клик:</p>
      </div>
      <div class="inf-schet inf-teg">
        <h1>{{ click }}</h1>
        <p>Рублей</p>
      </div>
      <div class="inf-level inf-teg">
        <h1>{{ level }} </h1>
        <p>Лвл</p>
      </div>
    </div>
    <div class="content-click">
      <button @click="clicker">Зарабатывать деньги!</button>
    </div>
    <div class="content-shop">
      <div class="shop-x1 shop-x" @click="levelUp1">
        <p>+1</p>
        <p>цена: 10</p>
      </div>
      <div class="shop-x2 shop-x" @click="levelUp2">
        <p>+2</p>
        <p>цена: 20</p>
      </div>
      <div class="shop-x2 shop-x" @click="levelUp3">
        <p>+3</p>
        <p>цена: 30</p>
      </div>
    </div>
    <div class="iphone">
      <div class="iphone-content" @click='levelUpIphon'>
        <div class="iphone__img">
          <img src="./assets/iphone.png" alt="айфон" />
        </div>
        <div class="iphone__text">
          <p>Купить маме айфон!</p>
          <p>Цена: 100.000</p>
        </div>
      </div>
      <div class="iphone-inf">
        <p>Айфонов у Мамы:</p>
        <h1>{{ iphone }}</h1>
      </div>

    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      click: 97841,
      up: 1,
      level: 0,
      iphone: 0
    }
  },
  methods: {
    levelUp1() {
      if (this.click > 10) {
        this.click -= 10
        this.up++
        this.level++
      }
    },
    levelUp2() {
      if (this.click > 20) {
        this.click -= 20
        this.up += 2
        this.level++
      }
    },
    levelUp3() {
      if (this.click > 30) {
        this.click -= 30
        this.up += 3
        this.level++
      }
    },
    levelUpIphon() {
      if (this.click > 100000) {
        this.click -= 100000
        this.iphone += 1
      }
    },
    clicker() {
      this.click += this.up
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Jost:wght@500&family=Lato:wght@300;400&family=Noto+Sans+SC:wght@300&display=swap');

// Настройки страницы
html {
  font-family: 'Noto Sans SC', sans-serif;
  // background-color: rgb(246, 224, 100);
  background: -webkit-linear-gradient(90deg, #efcaff, #e2bbfe, #e2b3fe);
  background: linear-gradient(90deg, #efcaff, #e2bbfe, #e2b3fe);

}

* {
  margin: 0;
  padding: 0;
}

.content {
  &-shop {
    display: flex;
  }

  // Информация об игре
  .content-inf {
    display: flex;
    justify-content: space-around;

    .inf-teg {
      h1 {
        text-align: center;
      }

      p {
        text-align: center;
      }
    }

    .inf-schet {
      font-size: 32px;
      // color: #F67B44;
      color: cornflowerblue;
    }

    .inf-up {
      font-size: 16px;
      // color: #f65044;
      color: cornflowerblue;
    }

    .inf-level {
      font-size: 16px;
      // color: #f65044;
      color: cornflowerblue;
    }
  }

  // Кнопка кликера
  .content-click {
    display: flex;
    justify-content: center;
    align-items: center;

    button {
      width: 50%;
      height: 100px;

      // background: rgb(252, 197, 88);
      background-color: white;
      // color: #f65044;
      color: cornflowerblue;

      font-size: 24px;
      border: none;
      border-radius: 60px;
    }
  }

  // Прокачка
  .content-shop {
    width: 60%;
    margin: 20px auto;

    justify-content: space-between;


    .shop-x {
      width: 80px;
      height: 80px;
      margin-left: 10px;

      font-size: 18px;

      // background: rgb(252, 197, 88)
      background-color: white;
      // color: #f65044;
      color: cornflowerblue;

      border-radius: 50%;
      user-select: none;

      p {
        text-align: center;
        margin: 0;
        padding: 0;
      }
    }
  }

  // Купить Айфон
  .iphone {
    width: 50%;
    height: auto;
    margin: 0 auto;

    .iphone-content {
      width: 220px;
      height: 220px;

      margin: 0 auto;
      border-radius: 35%;

      display: flex;
      flex-direction: column;
      align-items: center;

      // background: rgb(252, 197, 88);
      background-color: white;
      user-select: none;

      img {
        height: 160px;
        width: 180px;
      }

      p {
        text-align: center;
        // color: #f65044;
        color: cornflowerblue;
      }
    }

    .iphone-inf {
      width: 100%;
      height: 100px;
      margin: 0 auto;

      display: flex;
      align-items: flex-end;
      justify-content: center;

      p {
        height: 40px;
        margin-bottom: 0;

        font-size: 32px;
        // color: #F67B44;
        color: cornflowerblue;
      }

      h1 {
        height: 80px;

        font-size: 70px;
        // color: #f65044;
        color: cornflowerblue;
      }
    }
  }
}
</style>