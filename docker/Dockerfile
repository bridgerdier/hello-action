FROM docker.io/eclipse-temurin:20-jre
LABEL authors="info@predic8.de"
ARG USERNAME=membrane
ARG USER_UID=1000
ARG USER_GID=$USER_UID

COPY target/hello-action*.jar .

# Create the user
RUN groupadd --gid $USER_GID $USERNAME && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

USER $USERNAME
ENTRYPOINT ["java", "-jar", "hello-action-0.0.1-SNAPSHOT.jar"]