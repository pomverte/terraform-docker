FROM rrey/azdo-base-container:v0.1.2

ENV TERRAFORM_RELEASE_URL=https://releases.hashicorp.com/terraform

ENV TERRAFORM_VERSION=0.14.4
ENV TERRAFORM_SHA256SUM=042f1f4fb47696b3442eca12bce7cce6de0b477b299503ddad6b8bc3777a54b5

RUN wget "${TERRAFORM_RELEASE_URL}/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip" && \
    wget "${TERRAFORM_RELEASE_URL}/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_SHA256SUMS" && \
    grep terraform_${TERRAFORM_VERSION}_linux_amd64.zip terraform_${TERRAFORM_VERSION}_SHA256SUMS > SHA256SUMS && \
    sha256sum -c SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/

CMD [ "terraform", "version" ]
