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

      <div class="content_mission">
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
    </div>

  </div>
  </body>
  </html>
</template>


<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

