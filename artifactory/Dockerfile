FROM releases-docker.jfrog.io/jfrog/artifactory-jcr:7.35.2

USER root
COPY rootca_vtdc.crt /etc/pki/ca-trust/source/anchors/

RUN update-ca-trust
USER 1030
