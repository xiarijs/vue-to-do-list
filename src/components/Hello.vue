<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table cellpadding="0" cellspacing="0" border="0" class="add_table">
      <tbody>
        <tr>
          <td>名称</td>
          <td class="tl"><input type="text" v-model="data.name"></td>
          <td>图片</td>
          <td colspan="3" class="tl"><input type="text" v-model="data.img"></td>
        </tr>
        <tr>
          <td>链接</td>
          <td class="tl"><input type="text" v-model="data.url"></td>
          <td>楼层位置</td>
          <td class="tl"><input type="text" v-model="data.floor"></td>
          <td>旺旺ID</td>
          <td class="tl"><input type="text" v-model="data.wangwang"></td>
        </tr>
        <tr>
          <td colspan="6">
            <a href="javascript:;">保存</a>
            <a href="javascript:;">清空</a>
          </td>
        </tr>
      </tbody>
    </table>
    <h1>{{ msg2 }}</h1>
    <table cellpadding="0" cellspacing="0" border="0">
      <thead>
        <tr>
          <th>名称</th>
          <th>图片</th>
          <th>链接</th>
          <th>楼层位置</th>
          <th>旺旺ID</th>
          <th>操作</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in list">
          <td v-text="item.name"></td>
          <td v-text="item.img"></td>
          <td><a href="{{item.url}}" target="_blank" v-text="item.url"></a></td>
          <td v-text="item.floor"></td>
          <td v-text="item.wangwang"></td>
          <td><a href="javascript:;" title="删除" v-on:click="deleteData(item)">x</a></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data:function () {
    return {
      msg   : '添加商品',
      msg2  : '商品列表',
      data  : {
        name      : '',
        img       : '',
        url       : '',
        floor     : '',
        wangwang  : ''
      },
      list: [
          {
            id        : 1,
            name      : '商品名称1',
            img       : 'image.png',
            url       : 'http://www.baidu.com',
            floor     : '一年级',
            wangwang  : 'test'
          },
          {
            id        : 2,
            name      : '商品名称',
            img       : 'image.png',
            url       : 'http://www.baidu.com',
            floor     : '一年级',
            wangwang  : 'test'
          },
          {
            id        : 3,
            name      : '商品名称',
            img       : 'image.png',
            url       : 'http://www.baidu.com',
            floor     : '一年级',
            wangwang  : 'test'
          },
          {
            id        : 4,
            name      : '商品名称',
            img       : 'image.png',
            url       : 'http://www.baidu.com',
            floor     : '一年级',
            wangwang  : 'test'
          },
          {
            id        : 5,
            name      : '商品名称',
            img       : 'image.png',
            url       : 'http://www.baidu.com',
            floor     : '一年级',
            wangwang  : 'test'
          },
          {
            id        : 6,
            name      : '商品名称',
            img       : 'image.png',
            url       : 'http://www.baidu.com',
            floor     : '一年级',
            wangwang  : 'test'
          }
      ]
    }
  },
  methods : {
    deleteData : function(item){
      if(confirm('删除后不可恢复，确定删除？')){
        var _index = this.list.indexOf(item);
        if(_index!=-1){
          this.list.splice(_index,1);
          console.log(111)
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
table{ width: 100%; margin-top: 20px; border-collapse: collapse; }
table th,table td{ line-height: 32px; border: 1px solid #999; }
.add_table{ width: 960px; margin: 0 auto; }
.add_table td{ padding: 5px 10px; }
.add_table .tl{ text-align: left; }
</style>
