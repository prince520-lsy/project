<template>
  <div>
    全选 <input type="checkbox" v-model="isAll"><button>反选</button>
    <ul>
      <li v-for="item in person" :key="item.name">
        <input type="checkbox" v-model="item.checked">{{item.name}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      person: [
        {
          name: '悟空',
          checked: false
        },
        {
          name: '八戒',
          checked: false
        }, {
          name: '砂层',
          checked: false
        }, {
          name: '白龙',
          checked: false
        },
      ]
    }
  },
  computed: {
    isAll: {
      get() {
        let all;
        this.person.forEach((item) => {
          if (item.checked === false) {
            all = false
          }
        })
        if (all === undefined) {
          return true
        }
        else {
          return false
        }
      },
      set(value) {
        this.person.forEach((i) => {
          i.checked = value
        })
      }

    }

  },
  methods: {
    for() {
      this.person.forEach((item) => {
        item.name
      })
    }
  }
}

</script>

<style>

</style>