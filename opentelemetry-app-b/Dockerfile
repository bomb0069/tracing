FROM openjdk:11-jre
RUN mkdir -p /app/bin
COPY ./target/opentelemetry-app-b.jar /app/bin
COPY opentelemetry-javaagent-all.jar /app/bin
CMD java -Dotel.metrics.exporter=otlp \
         -Dotel.exporter.otlp.endpoint=otel-collector:4317 \
         -javaagent:/app/bin/opentelemetry-javaagent-all.jar \
		 -jar \
		 /app/bin/opentelemetry-app-b.jar
