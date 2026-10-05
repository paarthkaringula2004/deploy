FROM prom/prometheus:v3.15.0

COPY prometheus.yml /etc/prometheus/prometheus.yml
COPY alerts.yml /etc/prometheus/alerts.yml
RUN promtool check rules /etc/prometheus/alerts.yml && promtool check config /etc/prometheus/prometheus.yml

EXPOSE 9090
CMD ["--config.file=/etc/prometheus/prometheus.yml","--storage.tsdb.path=/prometheus","--web.listen-address=0.0.0.0:9090"]
