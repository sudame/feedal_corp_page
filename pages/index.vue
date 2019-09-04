<template>
  <html>
  <body>
  <div class="container">

<!--    header-->
    <header>
        <img src="feedal_logo.jpg">
        <nav>
          <ul class="navigation">
            <li>ミッション</li>
            <li>サービス</li>
            <li>ニュース</li>
            <li>会社情報</li>
            <li>お問い合わせ</li>
          </ul>
        </nav>
    </header>

<!--top画面(一番初めに表示される画面)-->
    <div id="top">
      <div class="bg"></div>
      <p>
        だれもが、<br><br><br>
        "どんな情報でも”、”気軽に”、”すぐに”<br><br><br>
        収集できる世界へ
      </p>
    </div>

<!--    mission 画面-->
    <div id="mission">
      <div class="title">Mission</div>
      <div class ="flexbox">
        <img src="feedal_mission.jpg">
        <div id="mission_title">
          エンジニアの <br>
            インプットに <br>
             革命を起こす
        </div>
      </div>

      <div class="content">
        <p>情報技術が年々発展していくに伴い、世界に存在する情報量は莫大なものになり、<br>
        エンジニアが学ぶべきことはそれに比例して多くなっています。<br><br>
        -- 混沌とする情報から自分の欲しい情報だけを手に入れることが難しい --<br><br>
        -- 世の中の流行の移動が速すぎてついていけない --<br><br>
        そんな経験ありませんか？<br><br><br>
        私たちFeedal は、<br><br>
        エンジニアの需要が高まっている世の中で、<br>
        このような課題を解決すべく、<br><br>
        "どれだけ良い情報をすばやく手に入れられるか"というインプットのインフラを作ります。</p>
      </div>

    </div>

<!--    service 画面-->
    <div id="service">
      <div class="title">Service</div>
      <div class="image">
        <img src="feedal_service.png">
      </div>
      <div id="service_title">Feedal</div>
      <div class="content">
        Feedal は、<br>
        あらゆるテクノロジーニュースをシェアし、<br>
        カテゴリごとにキャッチできるサービス<br>
        です。<br><br>
        Feedal を使えば、<br>
        自分の興味のあるIT分野のトレンド情報を毎日watchできます。<br>
        人から、常に最新で有意義な情報を得ることでエンジニアのあなたのインプットを充実させます。
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

  </div>
  </body>
  </html>
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
        ]
      }
    }
}
</script>

