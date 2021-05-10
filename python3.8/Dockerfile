FROM python:3.8.7-alpine3.12

RUN apk add --no-cache --update \
    curl \
    git

ENV TERRAFORM_VERSION=0.14.11
ENV TERRAFORM_SHA256SUM=171ef5a4691b6f86eab524feaf9a52d5221c875478bd63dd7e55fef3939f7fd4

RUN curl -fsSL -O https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    echo "${TERRAFORM_SHA256SUM}  terraform_${TERRAFORM_VERSION}_linux_amd64.zip" > terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    sha256sum -c terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/

CMD [ "terraform", "version" ]
