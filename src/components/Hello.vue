<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      姓名：<input type="text" style=" width:50px;" v-model="data.name">
      姓别：<label for="nan"><input type="radio" id="nan" name="sex">男</label><label for="nv"><input type="radio" id="nv" name="sex">女</label>
      班级：<select name="" id=""><option>请选择</option><option>一年级</option><option>二年级</option><option>三年级</option></select>
      年龄：<input type="text" style=" width:50px;">
      <input type="button" value="添加">
    </div>
    <table cellpadding="0" cellspacing="0" border="0">
      <thead>
        <tr>
          <th>姓名</th>
          <th>性别</th>
          <th>班级</th>
          <th>年龄</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in list">
          <td v-text="item.name"></td>
          <td v-text="item.sex"></td>
          <td v-text="item.cname"></td>
          <td v-text="item.age"></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data:function () {
    return {
      msg: 'This is to do list',
      data : {
        name : '2',
        sex  : '',
        cname: '',
        age  : ''
      },
      list: [
          {
            name  : '张三',
            sex   : '男',
            cname : '一年级',
            age   : '8' 
          },
          {
            name  : '张三',
            sex   : '男',
            cname : '一年级',
            age   : '8' 
          },
          {
            name  : '张三',
            sex   : '男',
            cname : '一年级',
            age   : '8' 
          },
          {
            name  : '张三',
            sex   : '男',
            cname : '一年级',
            age   : '8' 
          },
          {
            name  : '张三',
            sex   : '男',
            cname : '一年级',
            age   : '8' 
          },
          {
            name  : '张三',
            sex   : '男',
            cname : '一年级',
            age   : '8' 
          }
      ]
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
</style>
