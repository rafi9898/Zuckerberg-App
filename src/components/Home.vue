<template>
  <div class="home container">
    <div class="row">
        <div class="col s12">
          <div class="main-card">
          <div class="card white">
            <div class="card-content black-text">
              <div class="hero-photo">
                <img class="responsive-img circle" src="static/img/mark-zuckerberg.jpg">
              </div>
              <span class="card-title">Spend Mark Zuckerberg Money</span>
            </div>
          </div>
          </div>
        </div>

        <div class="col s12 main-money-card">
          <div class="money-card">
          <div class="card">
            <div class="card-content black-text">
              <span class="card-title">${{ totalMoney }}</span>
            </div>
          </div>
          </div>
        </div>

        <div class="col s12 m12 l12" v-for="(item, index) in items" :key="index">
          <div class="item-card">
          <div class="card">
            <div class="card-content black-text">
              <div class="img-item">
                <img :src="item.img" :alt="item.title">
              </div>
              <span class="card-title">{{ item.title }}</span>
              <span class="card-price">${{ item.price }}</span>

              <div class="btn-controls">
                <button @click="itemSell(index)" class="waves-effect waves-light btn blue darken-4 sell">SELL</button>
                <input type="number" min="0" v-model="item.count" disabled />
                <button @click="itemBuy(index)" class="waves-effect waves-light btn green darken-3 buy">BUY</button>
              </div>

              <span v-if="item.noMoney" class="alert">{{ alert }}</span> <br />
            </div>
          </div>
          </div>
        </div>

        <div class="purchased-items">
          <div class="col s12">
            <div class="items-box">
              <h2 class="main-title">Purchased Items</h2>
              <ul v-for="(purItem, index) in items" :key="index">
                <li v-if="purItem.count > 0">
                  <img :src="purItem.img">
                  <span class="title">{{ purItem.title }}</span>
                  <span class="count">x{{ purItem.count }}</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      totalMoney: 70000000000,
      alert: 'You do not have enough funds on your account!',
      searchTerm: '',
      items: [
        {
          img: 'static/items/bigmac.png',
          title: 'Big Mac',
          price: 2,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/cupofcoffee.jpg',
          title: 'Cup of Coffee',
          price: 4,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/book.jpg',
          title: 'Book',
          price: 15,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/headphones.png',
          title: 'Headphones',
          price: 200,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/airjordans.png',
          title: 'Air Jordans',
          price: 200,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/skateboard.png.jpg',
          title: 'Skateboard',
          price: 300,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/smartphone.png.jpg',
          title: 'Smartphone',
          price: 600,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/gamingconsole.png',
          title: 'Gaming Console',
          price: 600,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/bike.png.jpg',
          title: 'Bike',
          price: 800,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/jetski.png.jpg',
          title: 'Jet Ski',
          price: 8000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/4ktv.png.jpg',
          title: '4K TV',
          price: 10000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/rolex.png',
          title: 'Rolex',
          price: 15000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/foodtruck.png',
          title: 'Food Truck',
          price: 50000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/tesla.png.jpg',
          title: 'Tesla',
          price: 70000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/helicopter.png',
          title: 'Helicopter',
          price: 175000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/ferrari.png.jpg',
          title: 'Ferrari',
          price: 200000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/lamborghini.png.jpg',
          title: 'Lamborghini',
          price: 200000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/townhouse.png',
          title: 'Townhouse',
          price: 200000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/pizzashop.png.jpg',
          title: 'Pizza Shop',
          price: 500000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/superbowlad.png.jpg',
          title: 'Superbowl Ad',
          price: 5000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/beachhouse.png.jpg',
          title: 'Beach House',
          price: 5000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/yacht.png.jpg',
          title: 'Yacht',
          price: 10000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/f16.png',
          title: 'F16',
          price: 15000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/skyscraper.png',
          title: 'Skyscraper',
          price: 50000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/monalisa.png.jpg',
          title: 'Mona Lisa',
          price: 780000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/cruiseship.png.jpg',
          title: 'Cruise Ship',
          price: 1200000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/nbateam.png.jpg',
          title: 'NBA Team',
          price: 1300000000,
          count: 0,
          noMoney: false
        },
        {
          img: 'static/items/nflteam.png',
          title: 'NFL Team',
          price: 2300000000,
          count: 0,
          noMoney: false
        },
      ]
    }
  },
  methods: {
    itemBuy(id) {
      if(this.totalMoney >= this.items[id].price) {
        this.items[id].count++
        this.totalMoney -= this.items[id].price
        this.items[id].noMoney = false
      }
      else {
        this.items[id].noMoney = true
      }
      
    },
    itemSell(id) {
      if(this.items[id].count > 0) {
      this.items[id].count--
      this.totalMoney += this.items[id].price
      this.items[id].noMoney = false
    } else {
      this.items[id].count = 0;
      this.items[id].noMoney = false
    }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
  text-align: center;
}

.main-card .card {
  margin: 0 auto;
  margin-top: 30px;
  width: 100%;
  min-height: 35vh;
}

.main-card .card-title {
  font-weight: 550;
  font-size: 33px;
  letter-spacing: 0.4px;
  margin-bottom: 40px;
  color: #333;
}

.main-card .hero-photo img {
  width: 13%;
  margin-bottom: 20px;
  margin-top: 60px;
}

.money-card .card {
  background-color: #2ecc71;
  width: 100%;
  margin: 0 auto;
  margin-bottom: 20px;
}

.money-card .card-title {
  color: #FFF;
  font-size: 36px;
  font-weight: bolder;
  margin-top: 12px;
}

.item-card .card {
  width: 100%;
  min-height: 38vh;
}

.item-card {
  text-align: center;
}

.item-card .card-title {
  font-size: 25px;
  font-weight: 500;
}

.item-card .card-price {
  color: #2ecc71;
  font-size: 19px;
  font-weight: 500;
}

.img-item {
  text-align: center;
}

.img-item img {
  width: 150px;
}

.btn-controls {
  display: flex;
  justify-content: center;
}

.btn-controls input {
  width: 40%;
  text-align: center;
  -webkit-appearance: none; 
   -moz-appearance:textfield;
   margin: 0; 
}

.alert {
  color: red;
}

.purchased-items .main-title {
  font-size: 22px;
}

.purchased-items .items-box {
  background-color: #FFF;
  width: 75%;
  margin: 0 auto;
  text-align: center;
  padding: 20px 20px;
}

.purchased-items .items-box li {
  display: flex;
  justify-content: center;
}

.purchased-items .items-box .title {
  font-size: 16px;
}

.purchased-items .items-box .count {
  font-size: 16px;
  font-weight: 550;
}

.purchased-items .items-box img {
  width: 70px;
  height: 70px;
  float: left;
}

.purchased-items .items-box .title {
  margin-top: 20px;
}

.actMoney {
  font-size: 18px;
  font-weight: 500;
  color: green;
}

.main-money-card {
  position: sticky;
  top: 0;
  z-index: 100;
}

@media (max-width: 1200px) {
.main-card .card-title {
  font-size: 28px;
}

.money-card .card-title {
  font-size: 28px;
}
}

@media (max-width: 993px) {
  .main-card .card {
  width: 83vw;
}

.money-card .card {
  width: 83vw;
  margin: 0 auto;
}
}

@media (max-width: 768px) {
.main-card .hero-photo img {
  width: 50%;
  margin-bottom: 15px;
}
.main-card .card-title {
  font-size: 22px;
}

.money-card .card-title {
  font-size: 22px;
}

.main-card .card {
  width: 82vw;
}

.money-card .card {
  width: 82vw;
  margin: 0 auto;
}
}

@media (max-width: 400px) {
  .hero-photo img {
  width: 70%;
  margin-bottom: 15px;
  }
}


</style>
