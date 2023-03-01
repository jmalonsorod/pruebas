# Imagen de dockerhub con Alpine y JRE 11
FROM eclipse-temurin:11-jre-alpine

# Informamos puerto usado
EXPOSE 8080

# Variables de entorno si son necesarias
ENV VARIABLE1 1

# NO lo hacemos asi, se gestiona en openshift en todo caso
#VOLUME /tmp

# Instalar cualqueir requisito previo
#ADD requirements.txt .
#RUN python -m pip install -r requirements.txt

# Fijamos directorio de trabajo y añadimos software necesario a la imagen
WORKDIR /app
#ADD . /app
COPY run.sh /app
COPY target/*.jar /app/app.jar
RUN chmod +x run.sh

# Cambiamos a un usuario que no sea root, creandolo previamente
#RUN useradd infra && chown -R infra /app
#USER infra

# Iniciamos la aplicacion
ENTRYPOINT ["run.sh"]
