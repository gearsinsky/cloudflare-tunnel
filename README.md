# cloudflare-tunnel

# only do once
## cloudflared tunnel login
這會打開瀏覽器認證，並把證書存在你的主機，如 ~/.cloudflared/cert.pem

## Cloudflared Tunnel create 
建立tunnel生成json憑證
## COPY TLS json
你要把它複製到 cloudflared/jenkins-tunnel.json（給 Docker 用）
## 綁定DNS
cloudflared tunnel route dns jenkins-tunnel jenkins.rising-shop-dg.com
必要條件：domain託管在cloudflare

## docker compose up -d 
curl -I http://{{config上面的hostname}}