<template>
  <div class="index">
    <div class="component">
      <ul class="align">
        <li>
          <figure class="book" 
          :style="bookHoverStyle"
          @mouseover="mouseOver"
          @mouseout="mouseOut"
          @mousemove="mouseMove"
          @click="openBook">
            <!-- Front -->

            <ul class="paperback_front" :class="{'paperback_front_active': openBookFlag}">
              <li>
                <!-- <span class="ribbon">Nº1</span> -->

                <img src="@/assets/cover.jpg" alt width="100%" height="100%" />
              </li>

              <li></li>
            </ul>

            <!-- side -->

            <ul class="book-side">
              <li></li>
            </ul>

            <!-- Pages -->

            <ul class="ruled_paper" :class="{'ruled_paper_active': openBookFlag}">
              <li>1111</li>
              <li>
                <p>林薇因说，任何东西都可被替代，爱情，往事，记忆，失望，时间......都可被替代，但是你，不能无力自拔。</p>
                <p>如果我不是你的独一无二，那我也绝不会非你不可。</p>
                <p>我不希望在我的余生里，你只能成为一段难忘的回忆。</p>
                <p>我希望每天清晨你和阳光都在，那就是我想要的未来。</p>
                <p>跟我走吧 。早安给你，晚安给你，忐忑给你，情书给你，不眠的夜给你，五月的清晨给你， 手给你，怀抱给你，车票给你，跋涉给你，等待给你 玫瑰给你， 心跳给你 ，彻夜长谈的星光给你， 临睡前的吻给你 ，冰淇淋的第一口给你，一腔孤勇和余生的六十年 全都给你。</p>
              </li>
              <li>
                <p>
                  又快到了3.18，去年到今年似乎发生了太多，朋友的背叛是让我对这个游戏失去热爱的导火线，有时候又舍不得离开这同我一起成长的青春记忆。
                  今天又再次回到上京，那个时代的记忆，一股脑的涌来，冬风已过十二月，丢失的东西还能回来吗。
                  同你一起走过的这些年，希望这个给予我所有童年回忆的第一个游戏可以永存，春有百花秋有月 ，夏有凉风冬有雪 ，若无闲事挂心头，便是人间好时节。
                  少年时第一次遇见，感觉好像已经认识了你七八百年，你还是个新型游戏，当时思潮漫天。我还未懂何是胡搅蛮缠，二十岁再见，你的时间还有多远。想到和你在一起的这些年里，好像什么都做过，记忆犹新，现在再想起来的时候，总觉得又傻又好笑，我们有太多太多的回忆，离开的四年，距离并不能隔阂感情。这些年有你让我感到幸福，但我也希望你变得更好且让我不虚此行。 
                  东方，飘散在雾中的紫禁城，热腾腾的包子，浓香的乌龙，精明的商人和神秘的大师，回神过来，却已经是留恋往返。
                  今天看了贴吧的一个帖子，看到了帖子里帖的上京的背景音乐，打开网易云听着，看着评论，突然感触良多，从前年我作为回归党回来，学会了随毛随名片挂机站街，但我似乎忘了自己的初心，我是有多久没有开背景音乐来怀念了呢，网易云里面有句话写得很好：四年级夏日，24空调，三四块西瓜，一整个彩虹岛，循环一遍所有的歌，像独自旅行一般，最后还是回到上京。我只希望这个游戏永远不要倒闭，哪怕苟延残喘也让我继续爱着它。
                </p>
              </li>
              <li>3333</li>
              <li>4444</li>
            </ul>
            <!-- Back -->
            <ul class="paperback_back">
              <li>
                <img src="@/assets/cover.jpg" alt width="100%" height="100%" />
              </li>

              <li></li>
            </ul>
          </figure>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  components: {},
  data () {
    return {
      openBookFlag: false,
      bookHoverStyle: null
    }
  },
  methods: {
    openBook () {
      this.openBookFlag = true
    },
    mouseOver (evente) {

    },
    mouseMove (event) {
      console.log(event)
      let
      wHeight = 580,
      wWidth = 400,
      currentMouseX = event.pageX,
      currentMouseY = event.pageY,
      around1 = -1 * (currentMouseY * 100 / wHeight * 0.2 - 15) + 'deg',
      around2 = 1 * (currentMouseX * 100 / wWidth * 0.2 - 15) + 'deg',
      trans1 = (currentMouseX * 100 / wHeight * 0.3 ) + 'px',
      trans2 = (currentMouseY * 100 / wHeight * 0.3 ) + 'px'

      // this.bookHoverStyle = "animation-play-state:paused;transform: translate3d(" + trans1 + ", " + trans2 +", 0) scale(1) rotatex(" + around1 + ") rotatey(" + around2 + ")"
      this.bookHoverStyle = "animation: normal;transform: translate3d(" + trans1 + ", " + trans2 +", 0) scale(1) rotatex(" + around1 + ") rotatey(" + around2 + ")"
    },
    mouseOut (e) {
      console.log(e)
      // this.bookHoverStyle = "animation-play-state:running"
    }
  },
};
</script>

<style  scoped>
  @import '../common/normalize.css';
  @import '../common/demo.css';
  @import '../common/book.css';
  .ruled_paper > li {
    background-color: #fff;
    background-image: -webkit-linear-gradient(rgba(200, 200, 200, 0.1) 0.1em, transparent 0.1em), -webkit-linear-gradient(left, #e1ddd8 0%, #fffbf6 100%);
  }
  .ruled_paper > li:after {
    transform: rotateY(180deg) translateZ(1px);
    width: 100%;
    height: 100%;
    background-color: #fff;
    background-image: -webkit-linear-gradient(rgba(200, 200, 200, 0.1) 0.1em, transparent 0.1em), -webkit-linear-gradient(left, #e1ddd8 0%, #fffbf6 100%);
    position: absolute;
    left: 0;
    top: 0;
    z-index: -1;
  }
</style>
