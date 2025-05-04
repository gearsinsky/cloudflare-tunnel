# cloudflare-tunnel
## cloudflared tunnel login
```
cloudflared tunnel login
```
必須先確認好>開啟zero trust
這會打開瀏覽器認證>並把證書存在你的主機>如 ~/.cloudflared/cert.pem
## Cloudflared Tunnel create 
```
Cloudflared Tunnel create jenkins-tunnel
```
建立tunnel生成json憑證>存放在~/.cloudflared/
## COPY TLS json
```
你要把它複製到 >./jenkins-tunnel.json（給 Docker 用）
```
## 綁定DNS
```
cloudflared tunnel route dns jenkins-tunnel jenkins.rising-shop-dg.com
```

必要條件：domain託管在cloudflare
綁定之後檢查record，tls，policy要設定，不然訪問域名就可以連到了

## docker compose up -d 
```
curl -I http://{{config上面的hostname}}
```

## 測試
