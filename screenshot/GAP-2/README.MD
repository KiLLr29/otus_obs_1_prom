В ходе выполнения домашнего задания №4 Формирование dashboard на основе собранных данных с Grafana в мой стенд был добавлен контейнер с grafana:
  grafana:
    image: grafana/grafana:latest
    container_name: grafana
    restart: always
    ports:
      - "3000:3000"
    environment:
      GF_SECURITY_ADMIN_USER: admin
      GF_SECURITY_ADMIN_PASSWORD: admin
      GF_INSTALL_PLUGINS: grafana-clock-panel,grafana-simple-json-datasource
    volumes:
      - grafana_data:/var/lib/grafana
      - ./grafana/provisioning:/etc/grafana/provisioning
    networks:
      - wordpress_network

Добавлены необходимые source и dashboards, скрины прилагаются.