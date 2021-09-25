<template>
  <div id="wrapper">
    <div class="search">
      <a-input-search
        placeholder="input search text"
        enter-button
        @search="onSearch"
      />
    </div>
  </div>
</template>

<script>
import SystemInformation from './LandingPage/SystemInformation'

// import { Button } from 'ant-design-vue'
export default {
  name: 'landing-page',
  // components: {
  //   Button,
  // },
  data() {
    return {
      searchList: [],
    }
  },
  methods: {
    async onSearch(value) {
      let res = await this.$http.get(
        // 'https://weread.qq.com/web/search/search_suggest?keyword=${' +
        //   value +
        //   '}&count=40'
        `https://weread.qq.com/web/search/search_suggest?keyword=${value}&count=40`
      )
      this.searchList = res.data.records
      console.log(res)
      console.log(this.searchList)
    },
  },
}
</script>

<style></style>
