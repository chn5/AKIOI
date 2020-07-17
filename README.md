
<!DOCTYPE html>
<html>
    
    <head>
        <meta charset="utf-8">
        <title>AK IOI</title>
        <link href="style/main.css?ver=10" rel="stylesheet" type="text/css" encoding="utf-8">
        <link href="style/ai.css?ver=10" rel="stylesheet" type="text/css">
        <link href="https://cdn.jsdelivr.net/gh/xb2016/kratos-pjax@0.4.0/static/css/font-awesome.min.css?ver=4.7.0" rel="stylesheet" type="text/css">
        <link rel="shortcut icon" href="favicon.ico">
        <script src="https://cdn.jsdelivr.net/npm/jquery@3.2.1/dist/jquery.min.js"></script>
        <meta name="HandheldFriendly" content="True">
        <meta name="MobileOptimized" content="320">
        <meta name="viewport" content="width=device-width, target-densitydpi=160dpi, initial-scale=1.0, maximum-scale=1, user-scalable=no">
        <meta property="og:title" content="AK IOI 游戏" />
        <meta property="og:site_name" content="AK IOI 游戏" />
        <meta property="og:description" content="合并评测状态并获得AK！警告：该游戏非常容易上瘾" />
        <meta property="og:image" content="http://gabrielecirulli.github.io/2048/meta/og_image.png" />
        <style>
        .game-container {
            touch-action: none;
        }
        </style>
    </head>
    
    <body>
        <div class="mobile-top"></div>
        <div class="container">
            <div class="game-explanation game-list" style="pointer-events:none;position:absolute;padding-left:540px;padding-top:128px;">
                <table class="status-list">
                    <style>.status-list th,.status-list td{text-align:left;padding:4px;}</style>
                    <tr>
                        <th>评测状态</th>
                        <th>数值</th>
                    </tr>
                    <tr>
                        <td><span class="tile tile-2 example">CE</span><span class="game-list-label"><strong>C</strong>ompile <strong>E</strong>rror</span></td>
                        <td>2</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-4 example"><i class="fa fa-spin fa-circle-o-notch"></i></span><span class="game-list-label">Judging</span></td>
                        <td>4</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-8 example">RE</span><span class="game-list-label"><strong>R</strong>untime <strong>E</strong>rror</span></td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-16 example">TLE</span><span class="game-list-label"><strong>T</strong>ime <strong>L</strong>imit <strong>E</strong>xceeded</span></td>
                        <td>16</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-32 example">MLE</span><span class="game-list-label"><strong>M</strong>emory <strong>L</strong>imit <strong>E</strong>xceeded</span></td>
                        <td>32</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-64 example">ILE</span><span class="game-list-label"><strong>I</strong>dleness <strong>L</strong>imit <strong>E</strong>xceeded</span></td>
                        <td>64</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-128 example">OLE</span><span class="game-list-label"><strong>O</strong>utput <strong>L</strong>imit <strong>E</strong>xceeded</span></td>
                        <td>128</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-256 example">UKE</span><span class="game-list-label"><strong>U</strong>n<strong>K</strong>nown <strong>E</strong>rror</span></td>
                        <td>256</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-512 example">WA</span><span class="game-list-label"><strong>W</strong>rong <strong>A</strong>nswer</span></td>
                        <td>512</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-1024 example">PC</span><span class="game-list-label"><strong>P</strong>artially <strong>C</strong>orrect</span></td>
                        <td>1024</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-2048 example">AC</span><span class="game-list-label"><strong>AC</strong>cepted</span></td>
                        <td>2048</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-4096 example">PE</span><span class="game-list-label"><strong>P</strong>resentation <strong>E</strong>rror</span></td>
                        <td>4096</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-8192 example">DoJ</span><span class="game-list-label"><strong>D</strong>enial <strong>o</strong>f <strong>J</strong>udging</span></td>
                        <td>8192</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-16384 example">SJE</span><span class="game-list-label"><strong>S</strong>pecial <strong>J</strong>udge <strong>E</strong>rror</span></td>
                        <td>16384</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-32768 example">AU</span><span class="game-list-label"><strong>AU</strong></span></td>
                        <td>32768</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile-65536 example">AK</span><span class="game-list-label"><strong>AK</strong></span></td>
                        <td>65536</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile--1 example">#</span><span class="game-list-label"><strong>#</strong>pragma ...</span></td>
                        <td>×1</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile--2 example">O2</span><span class="game-list-label">-<strong>O2</strong></span></td>
                        <td>×2</td>
                    </tr>
                    <tr>
                        <td><span class="tile tile--4 example">O3</span><span class="game-list-label">-<strong>O3</strong></span></td>
                        <td>×4</td>
                    </tr>
                </table>
            </div>
            <div class="heading">
                 <h1 class="title">akioi</h1>

                <div style="float:right">
                  <div class="score-container">0</div>
                  <div class="best-container">0</div>
                </div>
            </div>
            <p class="game-intro">合并评测状态并得到<strong>AK</strong>！
                <a class="restart-button" style="float:right;">重新做人</a>
            </p>
            <div class="controls">
                <div id="hint-button-container">
                    <button id="hint-button" class="ai-button">获得提示</button>
                </div>
                <div id="feedback-container" href="javascript:void(0)" onclick="document.querySelector('#feedback-container').innerHTML='';"></div>
                <div id="run-button-container">
                    <button id="run-button" class="ai-button">手动模式</button>
                </div>
            </div>
            <div class="game-container">
                <div class="game-message">
                    <p></p>
                    <div class="lower">
                        <a class="retry-button">重玩</a>
                        <a class="score-sharing">提交成绩</a>
                    </div>
                </div>
                <div class="grid-container">
                    <div class="grid-row">
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                    </div>
                    <div class="grid-row">
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                    </div>
                    <div class="grid-row">
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                    </div>
                    <div class="grid-row">
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                        <div class="grid-cell"></div>
                    </div>
                </div>
                <div class="tile-container"></div>
            </div>
            <p class="game-explanation"> <strong class="important">玩法：</strong>使用<strong>方向键 或 手指划屏</strong>的方式移动方块。当相同状态的方块相撞，<strong>它们会合并成两倍数值的方块。</strong><a href="wiki/" target="_blank">详细信息</a>
            </p>
            <p>相关游戏：<a href="https://2048game.com/" target="_blank">原版2048</a> <a href="https://dimit.me/Fe26/index_zh_CN.html" target="_blank">死铁</a></p>
            <p>
                排行榜排名不正确的问题已经修复。
            </p>
            <p style="margin-top:8px;display:none;" class="game-explanation" id="getfixed"> <strong class="important">提示：</strong>iOS设备的滚动锁定功能存在问题。你可以<a href="javascript:void(0)" onclick="document.querySelector('html').style.position='fixed';">禁止滚动</a> 以获得更好的游戏体验。
            </p>
            <h2><center>排行榜</center></h2>
            <p style="margin-top:-8px;"><center>30天内的前50名&nbsp;<a href="javascript:void()" onclick="showrank()">刷新</a></center></p>
            <p class="ranklist-show-area"></p>
            <script>
                var rank_is_loading = false;
                function showrank() {
                    if(rank_is_loading) return;
                    rank_is_loading = true;
                    $showbox = $('.ranklist-show-area');
                    $showbox.html('正在加载...');
                    $.ajax({
                        type: "GET",
                        cache: false,
                        url: "data/ranklist.php",
                        dataType: "text",
                        error: function(e) {
                            console.log('排行加载失败：',e);
                            $showbox.html('加载失败');
                            rank_is_loading=false;
                        },
                        success: function(e) {
                            $showbox.html(e);
                            rank_is_loading=false;
                        }
                    });
                }
                showrank();
                function hideinfo() {
                    $('.ranklist-info').css('display','none');
                }
                function hideann() {
                    $('.ann-info').css('display','none');
                }
                function showinfo(id) {
                    $area = $('.info-code');
                    $box = $('.ranklist-info');
                    $.ajax({
                        type: "GET",
                        cache: false,
                        url: "data/get_info.php?gameid="+id,
                        dataType: "text",
                        error: function(e) {
                            console.log('详情加载失败：',e);
                            $area.html('加载失败');
                            $box.css('display','block');
                        },
                        success: function(e) {
                            $area.html(e);
                            $box.css('display','block');
                        }
                    });
                }
                function showann(id) {
                    $area = $('.ann-code');
                    $box = $('.ann-info');
                    $.ajax({
                        type: "GET",
                        cache: false,
                        url: "skip-announcement/"+id+".txt",
                        dataType: "text",
                        error: function(e) {
                            console.log('详情加载失败：',e);
                            $area.html('加载失败');
                            $box.css('display','block');
                        },
                        success: function(e) {
                            $area.html(e);
                            $box.css('display','block');
                        }
                    });
                }
            </script>
            <style>
                .ranklist-info,
                .ann-info {
                    position:fixed;
                    width:100%;
                    height:100%;
                    left:0;
                    top:0;
                    background-color:rgba(0,0,0,0.5);
                    z-index:500;
                    /*overflow-y:scroll;*/
                    padding:16px;
                    display:block;
                }
                .ranklist-info-inner,
                .ann-info-inner{
                    width: calc(100% - 56px);
                    height: calc(100% - 56px);
                    background-color:#FFF;
                    z-index:501;
                    padding:12px;
                }
                .code-block {
                    border:1px solid #666;
                    background-color: #EEE;
                    font-size:14px;
                    padding:4px;
                    overflow-x:scroll;
                    overflow-y:scroll;
                }
                .info-code,
                .ann-code{
                    width: calc(100% - 13px);
                    height: calc(100% - 45px);
                    margin-bottom:0px;
                }
            </style>
            <div class="ranklist-info" style="display:none;">
                <div class="ranklist-info-inner">
                    <h3 style="line-height:20%;margin-top:8px;"><a onclick="hideinfo()">×</a>&nbsp;记录详情</h3>
                    <pre class="code-block info-code">                        Test text
                    </pre>
                </div>
            </div>
            <div class="ann-info" style="display:none;">
                <div class="ann-info-inner">
                    <h3 style="line-height:20%;margin-top:8px;"><a onclick="hideann()">×</a>&nbsp;作弊处理通告</h3>
                    <pre class="code-block ann-code">                        Test text
                    </pre>
                </div>
            </div>
            <!--hr>
            Credits moved to wiki.
            <p>Created by <a href="http://gabrielecirulli.com" target="_blank">Gabriele Cirulli.</a> Based on <a href="https://itunes.apple.com/us/app/1024!/id823499224" target="_blank">1024 by Veewo Studio</a> and conceptually similar to <a href="http://asherv.com/threes/"
                target="_blank">Threes by Asher Vollmer.</a>

            </p>
            <p>AI solver by <a href="https://github.com/ov3y/65536-AI">Matt Overlan</a>

            </p>
            <div class="sharing"> <a href="https://localhost:1/share" class="twitter-share-button" data-text="Check out 65536, a game where you join numbers to score high! #65536game #65536ai" data-via="gabrielecirulli">Tweet</a>

                <script>
                ! function (d, s, id) {
                    var js, fjs = d.getElementsByTagName(s)[0],
                        p = /^http:/.test(d.location) ? 'http' : 'https';
                    if (!d.getElementById(id)) {
                        js = d.createElement(s);
                        js.id = id;
                        js.src = p + '://localhost:1/widgets.js';
                        fjs.parentNode.insertBefore(js, fjs);
                    }
                }(document, 'script', 'twitter-wjs');
                </script> <span class="btc-donate">
        <a href="bitcoin:1Ec6onfsQmoP9kkL3zkpB6c5sA4PVcXU2i">
          <img src="meta/icon_bitcoin.png">Donate
        </a>
        <span class="address"><code>1Ec6onfsQmoP9kkL3zkpB6c5sA4PVcXU2i</code></span>
</span>
            </div>
        </div-->
        </div>
        <script src="js/animframe_polyfill.js"></script>
        <script src="js/hammer.min.js"></script>
        <script src="js/keyboard_input_manager.js?ver=10"></script>
        <script src="js/html_actuator.js?ver=10"></script>
        <script src="js/grid.js?ver=28"></script>
        <script src="js/tile.js"></script>
        <script src="js/game_manager.js?ver=19"></script>
        <script src="js/application.js?ver=13"></script>
        <!--script src="js/all.js"></script-->
        <script src="js/ai.js?ver=25"></script>
        <!--script src="https://cdn.luogu.org/js/jquery-2.1.1.min.js"></script-->
        <script>
          function IsPC(){    
            var userAgentInfo = navigator.userAgent;  
            var Agents = new Array("Android", "iPhone", "SymbianOS", "Windows Phone", "iPad", "iPod");    
            var flag = true;
            for (var v = 0; v < Agents.length; v++) {    
              if (userAgentInfo.indexOf(Agents[v]) > 0) { flag = false; break; }    
            }    
            return flag;    
          }
          if(!IsPC()) document.getElementById("cheat-how").style.display="none";
          var u = navigator.userAgent;
          var isiOS = !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/);
          if(!isiOS) document.getElementById("getfixed").style.display="none";
        </script>
        <script>
        (function (i, s, o, g, r, a, m) {
            i["GoogleAnalyticsObject"] = r;
            i[r] = i[r] || function () {
                (i[r].q = i[r].q || []).push(arguments)
            }, i[r].l = 1 * new Date();
            a = s.createElement(o),
            m = s.getElementsByTagName(o)[0];
            a.async = 1;
            a.src = g;
            m.parentNode.insertBefore(a, m)
        })(window, document, "script", "//www.google-analytics.com/analytics.js", "ga");

        ga("create", "UA-42620757-2", "gabrielecirulli.github.io");
        ga("send", "pageview");
        </script>
    </body>

</html>
