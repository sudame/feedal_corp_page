<template>
  <div class="container">
    <link href="https://use.fontawesome.com/releases/v5.6.1/css/all.css" rel="stylesheet">
<!--    header-->
    <header>
        <img src="/feedal_logo.jpg">

<!--      ハンバーガーメニー-->
      <div class="header__menu__line" @click="naviOpen" :class="{'is-active': active}">
        <span></span>
        <span></span>
        <span></span>
      </div>

<!--      PC用のナビ header に含める-->
        <nav class="pc_nav">
          <ul>
            <li><a href="#mission">ミッション</a></li>
            <li><a href="#service">サービス</a></li>
            <li><a href="#news">ニュース</a></li>
            <li><a href="#company">会社情報</a></li>
            <li><a href="#contact">お問い合わせ</a></li>
          </ul>
        </nav>
    </header>

<!--    スマホ用のナビ headerに含めない-->
    <transition name="navi">
      <nav class="phone_nav" v-show="navi">
        <ul>
          <li><a href="#mission" @click="naviOpen">ミッション</a></li>
          <li><a href="#service" @click="naviOpen">サービス</a></li>
          <li><a href="#news" @click="naviOpen">ニュース</a></li>
          <li><a href="#company" @click="naviOpen">会社情報</a></li>
          <li><a href="#contact" @click="naviOpen">お問い合わせ</a></li>
        </ul>
      </nav>
    </transition>

<!--top画面(一番初めに表示される画面)-->
    <div id="top">
      <div class="bg"></div>
      <p>
        だれもが、<br><br><br>
        “どんな情報でも”、“気軽に”、“すぐに”<br><br><br>
        収集できる世界へ
      </p>
    </div>

<!--    mission 画面-->
    <div id="mission">
      <div class="title">Mission</div>
      <div class ="flexbox">
        <img src="/feedal_mission.jpg">
        <div id="mission_title">
          エンジニアの <br>
            インプットに <br>
             革命を起こす
        </div>
      </div>

      <div class="content">
        <p>情報技術が年々発展していくに伴い、世界に存在する情報量は莫大なものになり、<br>
        エンジニアが学ぶべきことはそれに比例して多くなっています。<br><br>
        ー 混沌とする情報から自分の欲しい情報だけを手に入れることが難しい ー<br><br>
        ー 世の中の流行の遷移が速すぎてついていけない ー<br><br>
        そんな経験ありませんか？<br><br><br>
        私たちFeedal は、<br><br>
        このような課題を解決すべく、<br><br>
          “より良い情報をすばやく手に入れられる” インプットのインフラを作ります。</p>
      </div>

    </div>

<!--    service 画面-->
    <div id="service">
      <div class="title">Service</div>
      <div class="image">
        <img src="/feedal_service.png">
      </div>
      <div id="service_title">Feedal</div>
      <div class="content">
        Feedal は<br>
        あらゆるテクノロジーニュースをシェアし、<br>
        カテゴリごとにキャッチできるサービス<br>
        です。<br><br>
        Feedal を使えば、<br>
        自分の興味のあるIT分野のトレンド情報を毎日watchできます。<br>
        他ユーザーを通じて、常に最新で有意義な情報を得ることでエンジニアのあなたのインプットを充実させます。
      </div>

      <div class="detail"><a href="https://feedal.com"> 詳しく見る</a></div>
    </div>

<!--    news画面-->
    <div id="news">
      <div class="title">News</div>
       <table border="0" v-for = "event in news_events" v-bind:key="event.date" id="news_event">
         <tbody>
        <tr>
          <td class="td1">{{event.date}}</td>
          <td class="td2" style="white-space:pre-line">{{event.content}}
          <a :href="event.atag">{{event.atag_title}}</a> </td>
        </tr>
        </tbody>
      </table>
    </div>

<!--    company画面-->
    <div id="company">
      <div class="title">Company</div>

      <p class="company_topic">社名</p>
      <p class="company_content">株式会社Feedal (英語名: Feedal Inc)</p>
      <p class="company_topic">代表者</p>
      <p class="company_content">代表取締役　　和木勇人</p>
      <p class="company_topic">本所所在地</p>
      <p class="company_content">茨城県つくば市天久保3丁目21-3 星谷ビル2-A
      </p>
      <p class="company_topic">設立</p>
      <p class="company_content">2019年7月26日</p>
      <p class="company_topic">事業内容</p>
      <p class="company_content">「Feedal」の開発・運営</p>
    </div>

<!--    contact画面-->
    <div id="contact">
      <div class="title">Contact</div>
      <p>
        弊社サービスのご利用に関するお問い合わせございましたら、お気軽にご連絡ください。<br><br>
        Mail: corp@feedal.com
      </p>
        <ul class="sns">
          <li><a href=""> <i class="fab fa-twitter-square fa-4x"></i></a></li>
          <li><a href=""> <i class="fab fa-facebook-square fa-4x"></i></a></li>
        </ul>
    </div>

<!--    footer画面-->
  <footer>
    <div>
     <p>@ 2019 Feedal Inc.<br><br></p>
     <p>このwebページではGoogle Analyticsを使用してアクセス情報を収集しています。<br>
      Google Analyticsについては
       <a href="https://policies.google.com/technologies/partner-sites?hl=ja">こちら</a> をご覧ください。<br><br></p>
      <p><a href="privacypolicy.pdf">プライバシーポリシー</a>    <a href="feedal_rule.pdf">利用規約</a> </p>
    </div>
  </footer>

  </div>
</template>


<script>
  import Vue from 'vue';

export default {
    data(){
      return{
        // newsのデータ
        news_events: [
            {date:'2019/07/15',content:'Feedal Meetup & LT大会 in Tsukuba #2 を行いました!',atag:'https://feedal.com/events/20190715/',atag_title:'特設ページはこちら'},
            {date:'2019/06/16',content:'Feedal Meetup in Tsukuba #1 を行いました!',atag:'https://twitter.com/feedal_inc/status/1140259783322136578?s=20',atag_title:'詳しくはこちら'}
        ],
          active:false,
          navi:false
      }
    },
    methods:{
        //ハンバーガーメニューが押されたときの挙動
      naviOpen:function () {
          this.active = !this.active;
          this.navi = !this.navi;
      },
    }
}
</script>

