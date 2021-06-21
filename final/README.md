# Crossy-Road

https://vincent0426.github.io/final

期末專題主題簡介:<br/>
這次期末專案是做一個可以在電腦或平板上玩的老遊戲crossy-road，有點類似老鼠過馬路，<br/>就是不能被車撞到然後會有一些障礙物擋著你，走越遠分數越高。<br/>

使用者要怎麼使用你的網站:<br/>
點開就可以玩了，使用電腦的話用方向鍵控制即可，若用平板的話可以點左下角的按鈕<br/>

專題中做了什麼，使用了什麼技術:<br/>
這次主要用了three.js 和 jquery<br/>
初始化背景的時候必須在按下start隱藏背景，這邊用的是jquery hide的寫法<br/>
https://stackoverflow.com/questions/16903605/hide-button-after-click-with-existing-form-on-page<br/>
而three.js則是整個遊戲的架構，其主要組成為以下:<br/>
* 建立場景 (通常透過 new THREE.Scene())
* 建立物件（mesh)
* 建立幾何形狀
* 建立材質
* 加入攝影機
* 加入燈光
* 呼叫 renderer.render 繪製場景。

根據上面的架構一步一步畫出來，先設定場景的大小後，開始個別製造要在螢幕上產生的物件，但這邊的做法是一個函式，因為不知道要產生多少個每次呼叫的時候再生成即可，像是車子、卡車、樹、主角等，這些都有所謂的geometry來決定形狀，因為three.js內建許多幾何形狀可以使用，在設定期meterial就是一些顏色等property，再加入這個scene，最難的地方是動畫的部分，要根據使用者的操作來控制要怎麼走，什麼時候要多生成lane什麼時候要消除，再來就是碰撞測試，要看使用者走的下一個是障礙物還是車子，如果是障礙物的話就會讓使用者的move停留在原地，如果是車子的話就會結束遊戲。

用svg來畫座標，這邊是畫好一組後，用旋轉的方式呈現<br/>
https://www.oxxostudio.tw/articles/201406/svg-04-path-1.html
