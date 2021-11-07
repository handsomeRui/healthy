<template>
  <div class="container" style="background: rgba(71, 132, 250)">
    <div class="first" style="background: rgba(71, 132, 250)">
      <div class="cueb" style="text-align: center">
        <img
          class="school"
          src="https://cueb-oss.oss-cn-guangzhou.aliyuncs.com/school.png"
        />
        <span style="font-weight: bold; font-size: 18px">首都经济贸易大学</span>
      </div>

      <div class="word" style="margin-left:10px" v-for="item in nameList" :key="item.key">
        <span class="gray">姓名</span>
        <span class="info">{{ item.name }}</span>
        <span class="gray" style="margin-left: 110px">          学工号</span>
        <span class="info">{{ item.numb }}</span>
      </div>

      <div style="margin-top: 20px;margin-left:10px">
        <span class="gray">单位</span>
        <span class="info">管理工程学院</span>
      </div>
    </div>

    <div class="second">
      <p
        style="
          font-size: 20px;
          font-weight: bold;
          text-align: center;
          margin-top: 10px;
          text-align: center;
        "
      >
        通行码
      </p>
      <p class="time">扫码时间：{{ nowTime }}</p>
      <div class="icon">
        <img
          style="margin-bottom: 10px"
          class="success"
          src="https://cueb-oss.oss-cn-guangzhou.aliyuncs.com/success.png"
        />
        <span style="font-size: 20px; font-weight: bold; color: green"
          >通行成功</span
        >
      </div>
    </div>

    <div class="third" style="font-size: 20px">
      <p
        style="
          margin-left: 145px;
          font-weight: bold;
          margin-top: 11px;
          positopn: absoulte;
        "
      >
        所在位置
      </p>
      <p class="line"></p>
      <p
        style="
          margin-left: 107px;
          font-size: 18px;
          margin-top: -12px;
          position: absolute;
          color: rgb(111, 158, 240);
        "
      >
        校本部-北门（入口）
      </p>
    </div>

    <div
      class="four"
      style="
        font-size: 16px;
        font-weight: normal;
        margin-left: 10px;
        position: absoulte;
        padding-top: 15px;
        padding-left: 10px;
      "
    >
      您的出入校申请时间如下：<br />
      出校时间 2021-11-04<br />
      入校时间 2021-11-15<br />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data () {
    return {
      nowTime: '',
      nameList: [
        { name: '陈冠瑞', numb: '22019207022', key: 0 }
        // { name: '朱艺', numb: '22019207040', key: 1 }
      ]
    }
  },
  mounted () {
    this.nowTimes()
  },
  methods: {
    nowTimes () {
      this.timeFormate(new Date())
      // setInterval(this.nowTimes, 10000)
      // this.clear()
    },
    // 显示当前时间（年月日时分秒）
    timeFormate (timeStamp) {
      const year = new Date(timeStamp).getFullYear()
      const month =
        new Date(timeStamp).getMonth() + 1 < 10
          ? '0' + (new Date(timeStamp).getMonth() + 1)
          : new Date(timeStamp).getMonth() + 1
      const date =
        new Date(timeStamp).getDate() < 10
          ? '0' + new Date(timeStamp).getDate()
          : new Date(timeStamp).getDate()
      const hh =
        new Date(timeStamp).getHours() < 10
          ? '0' + new Date(timeStamp).getHours()
          : new Date(timeStamp).getHours()
      const mm =
        new Date(timeStamp).getMinutes() < 10
          ? '0' + new Date(timeStamp).getMinutes()
          : new Date(timeStamp).getMinutes()
      const ss =
        new Date(timeStamp).getSeconds() < 10
          ? '0' + new Date(timeStamp).getSeconds()
          : new Date(timeStamp).getSeconds()
      // const week = new Date(timeStamp).getDay()
      // const weeks = ['日', '一', '二', '三', '四', '五', '六']
      // const getWeek = '星期' + weeks[week]
      this.nowTime =
        year + '-' + month + '-' + date + '' + ' ' + hh + ':' + mm + ':' + ss
    }
  }
}
</script>

<style scoped>
.container {
  height: 100vh;
  position: relative;
  height: 100%;
}

.first {
  width: 110%;
  height: 200px;
  position: fixed;
  z-index: -1;
  margin-left: -20px;
  margin-top:-10px
}

.school {
  margin-right: 10px;
  width: 50px;
  height: 50px;
}

.cueb {
  margin-top: 20px;
  display: flex;
  color: aliceblue;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  height: 40px;
}

.gray {
  color: rgb(143, 196, 232);
  font-size: 12px;
  font-weight: bold;
  margin-left: 25px;
  margin-top: 20px;
  margin-right: 10px;
}

.info {
  color: white;
  font-size: 14px;
  font-weight: bold;
}

.second {
  position: fixed;
  z-index: 1;
  background-color: rgb(255, 255, 255);
  width: 380px;
  height: 235px;
  margin-top: 150px;
  margin-left: 12px;
  border-radius: 3%;
}

.time {
  text-align: center;
  font-size: 16px;
  margin-top: 10px;
  color: rgb(80, 117, 221);
  font-weight: normal;
}

.success {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 80px;
  height: 80px;
}

.icon {
  margin-left: 145px;
  margin-top: 20px;
}

.third {
  position: fixed;
  z-index: 1;
  background-color: rgb(255, 255, 255);
  width: 380px;
  height: 100px;
  margin-top: 400px;
  border-radius: 3%;
  margin-left: 12px;
}

.line {
  width: 95%;
  height: 2px;
  margin-left: 10px;
  background: rgb(233, 233, 233);
}

.four {
  position: fixed;
  z-index: 1;
  background-color: rgb(255, 255, 255);
  width: 380px;
  height: 90px;
  margin-top: 515px;
  border-radius: 3%;
}
</style>
