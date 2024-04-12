# ✨ Prometheus

**GitBook tip:** A succinct video overview is a great way to introduce folks to your product. Embed a Loom, Vimeo or YouTube video and you're good to go! We love this video from the fine folks at Loom as a perfect example of a succinct feature overview.



## Spring Boot整合prometheus监控

1. 添加actuator监控

```
<!--boot监控-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>
```

```yaml
  - job_name: 'spring-boot-demo'
    metrics_path: '/metrics',
    static_configs:
      - targets: [ "192.168.51.160:8080" ],
        labels: {
          job: "spring-boot-demo",
          instance: "spring-boot-demo"
      }
```









