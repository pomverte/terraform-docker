FROM rrey/azdo-base-container:v0.1.2

ENV TERRAFORM_RELEASE_URL=https://releases.hashicorp.com/terraform

ENV TERRAFORM_VERSION=0.14.3
ENV TERRAFORM_SHA256SUM=aa7b6cb6f366ffb920083b2a9739079ee560240ca31b580fe422af4af28cbb5a

RUN wget "${TERRAFORM_RELEASE_URL}/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip" && \
    wget "${TERRAFORM_RELEASE_URL}/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_SHA256SUMS" && \
    grep terraform_${TERRAFORM_VERSION}_linux_amd64.zip terraform_${TERRAFORM_VERSION}_SHA256SUMS > SHA256SUMS && \
    sha256sum -c SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/

CMD [ "terraform", "version" ]
