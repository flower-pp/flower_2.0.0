<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col
        :span="3"
        class="left">
        <p>p.p家的花店</p>
      </el-col>
      <el-col
        :span="15"
        class="center">
        <div class="wrapper">
          <el-input
            v-model="search"
            placeholder="搜索商家或地点"
            @focus="focus"
            @blur="blur"
            @input="input"
          />
          <button class="el-button el-button--primary"><i class="el-icon-search"/></button>
          <dl
            v-if="isHotPlace"
            class="hotPlace"
          >
            <dt>热门搜索</dt>
            <dd
              v-for="(item, index) in $store.state.search.hotPlace.slice(0, 5)"
              :key="index">
              {{ item.name }}</dd>
          </dl>
          <dl
            v-if="isSearchList"
            class="searchList">
            <dd
              v-for="(item,index) in searchList"
              :key="index"
            >{{ item.name }}</dd>
          </dl>
        </div>
        <p class="suggest">
          <a
            v-for="(item, index) in $store.state.search.hotPlace.slice(0, 5)"
            :key="index"
            href="#"
          >{{ item.name }}</a>
        </p>
        <ul class="nav">
          <li>
            <nuxt-link
              to="/"
              class="takeout">玫瑰系列</nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="movie">花材搭配</nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="hotel">繁花系列</nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="apartment">绿植系列</nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="business">孩童系列</nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col
        :span="6"
        class="right"
      >
        <ul class="security">
          <li>
            <i class="refund"/><p class="txt">随时退</p>
          </li>
          <li>
            <i class="single"/><p class="txt">不满意免单</p>
          </li>
          <li>
            <i class="overdue"/><p class="txt">过期退</p>
          </li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>

<script>
    import _ from "lodash";
    export default {
      data(){
        return {
          search: '', //当前输入框的值
          isFocus: false, //是否聚焦
          hotPlace: [], // 热门搜索数据
          searchList: [] // 搜索数据
        }
      },
      computed:{
        isHotPlace(){
          return this.isFocus && !this.search
        },
        isSearchList(){
          return this.isFocus && this.search
        }
      },
      methods: {
        focus(){
          this.isFocus = true
        },
        blur(){
          setTimeout(()=>{
            this.isFocus = false
          }, 200)
        },
        input: _.debounce(async function(){
            let self = this;
            let city = self.$store.state.geo.position.city.replace('市', '');
            self.searchList = [];
            let {status, data: {top}} = await self.$axios.get('/search/top', {
              params: {
                input: self.search,
                city
              }
            })
            self.searchList = top.slice(0, 10);
        }, 300)
      }
    }
</script>

<style scoped>

</style>
