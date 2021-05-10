FROM rrey/azdo-base-container:v0.1.2

ENV TERRAFORM_RELEASE_URL=https://releases.hashicorp.com/terraform

ENV TERRAFORM_VERSION=0.14.11
ENV TERRAFORM_SHA256SUM=171ef5a4691b6f86eab524feaf9a52d5221c875478bd63dd7e55fef3939f7fd4

RUN wget --quiet "${TERRAFORM_RELEASE_URL}/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip" && \
    wget --quiet "${TERRAFORM_RELEASE_URL}/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_SHA256SUMS" && \
    grep terraform_${TERRAFORM_VERSION}_linux_amd64.zip terraform_${TERRAFORM_VERSION}_SHA256SUMS > SHA256SUMS && \
    sha256sum -c SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/

CMD [ "terraform", "version" ]
