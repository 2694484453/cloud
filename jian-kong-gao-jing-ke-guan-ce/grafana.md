# 💡 Grafana

{% hint style="info" %}
**GitBook tip:** A succinct video overview is a great way to introduce folks to your product. Embed a Loom, Vimeo or YouTube video and you're good to go! We love this video from the fine folks at Loom as a perfect example of a succinct feature overview.
{% endhint %}

## docker compose安装脚本

{% code title="" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```yaml
version: "3"
services:
  grafana:
    image: grafana/grafana:latest
    container_name: monitoring_grafana
    restart: unless-stopped
    links:
      - prometheus:prometheus
    volumes:
      - ./data/grafana:/var/lib/grafana
    environment:
      - GF_SECURITY_ADMIN_PASSWORD=MYPASSWORT
      - GF_USERS_ALLOW_SIGN_UP=false
      - GF_SERVER_DOMAIN=myrul.com
      - GF_SMTP_ENABLED=true
      - GF_SMTP_HOST=smtp.gmail.com:587
      - GF_SMTP_USER=myadrress@gmail.com
      - GF_SMTP_PASSWORD=mypassword
      - GF_SMTP_FROM_ADDRESS=myaddress@gmail.com
```
{% endcode %}
