<template>
  <div id="app" >
      <h2 style="margin-top: -50px" >调查问卷</h2>
      <h4 style="display: flex; flex-direction: column;" >
        <span > 尊敬的先生/女士; 为了更好的了解中小学生学习情况，我们特别展开这次调查。</span>
        <span>您的建议将会是我们创新项目的宝贵信息，非常感谢您抽出时间填写这份调查问卷！</span>
      </h4>
      <span id="fatherSpan"  v-for="(question,index) in questions" v-bind:key="question">
        <span class="childSpan" >{{index+1}}. {{question}}</span>   <br>
        <Qustion style="margin-top: -10px"  v-bind:answer="answers[index]" ></Qustion>
      </span>
    <span>
      <span class="childSpan" >13. {{special[0]}}</span>   <br>
      <Qustion style="margin-top: -10px"  v-bind:answer="special[1]"  class="childSpan" ></Qustion>
      <br>
      <Qustion style="margin-top: -15px" v-bind:answer="special[2]" class="childSpan"></Qustion>
    </span>
  </div>
</template>




<script>
import Qustion from "@/components/Question/Qustion";

export default {
  name: 'app',
  components: {
    Qustion
  },
  data() {
    return {
      questions:
          ['请问你的孩子在学习时能否保持较高效率？',
            '你是否感觉自己的孩子学习需要被强制监督？',
            '您平时是否有监督孩子写作业的时间？',
            '您平时一周中能抽出多少时间照看孩子写作业？',
            '您之前是否给孩子购买过学习机等学习助手？',
            '您之前是否通过远程监控等工具监督孩子学习？',
            '假如有一款可以监督孩子学习的软件，功能齐全且具有创新性，你会使用吗？',
            '您是否希望有一款智能机器来帮助您监督孩子学习？',
            '对于产品（一个桌面学习助手)的外观你偏向于哪种？',
            '如果有这么一款机器，您希望它有什么必须功能？（多选）',
            '如果有这么一款机器，您希望它有什么额外功能？（多选）',
            '对于这样一款机器，您的价格预期是多少？']

      ,
      answers :[
        ['能', '不能', '时而能，时而不能'] ,
        ['是', '否', '无所谓'] ,
        ['有', '无', '有时间但是没有监督', '没时间但是想监督'] ,
        ['2小时以下', '2小时到6小时', '6小时以上'] ,
        ['有', '无'] ,
        ['有', '无'] ,
        ['会使用', '不会使用'] ,
        ['是', '否'] ,
        ['卡通', '简约', '华丽', '小清新'] ,
        ['走神提醒', '反馈学习效率、专注度等情况', '迷你监控探头'] ,
        ['时钟', 'wifi通讯', '音乐播放器', '学习用具储放'] ,
        ['200及以下', '200-500', '500-800', '800-1000']
      ],
      special: ["如果有一款可以监督孩子学习的软件，您希望包括哪些方面？",  ['时间管理', '学习计划', '自我监控'],['目标调整', '习惯养成', '情感陪伴'] ]
    }
  }
}



</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.childSpan{
  margin-left: 40px;
  font-size: 15px;
  display: flex ;
  flex-direction: row
}
#fatherSpan{
  display: flex;
  flex-direction: column
}
</style>
