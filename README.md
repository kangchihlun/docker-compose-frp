# docker-compose-frp
frp service in docker-compose , one click to rock

# 自家用的內網穿透工具
### 建置步驟
- 找到第一台 server ，有固定 ip ，可以從外網用 22 port連線
- 使用 ip a 指令記下第一台的內網ip
- git 拉取本專案，假設目錄為 /home/docker-compose-frp
- 進到compose-frps，輸入 docker-compose -f compose-frps.yml up
- 找到第二台不能從外網連線的server，一樣拉取本專案
- 進到compose-frpc/，修改frpc/conf/frpc.ini 的目標ip
- 輸入 docker-compose -f compose-frpc.yml up

目前只有讓目標電腦監聽 22 port，如有需要再自行擴充。<br>
對外目前設定走 6000 port，意思就是說外網要訪問這台電腦的話就要打 <br> 
>ssh user@外網ip:6000 <br>
<a href="https://www.itread01.com/fefcf.html">如果要看frp詳細教學請看這裡</a>
