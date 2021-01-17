FROM python:3.8.7-alpine3.12

RUN apk add --no-cache --update \
    curl \
    git

ENV TERRAFORM_VERSION=0.14.4
ENV TERRAFORM_SHA256SUM=042f1f4fb47696b3442eca12bce7cce6de0b477b299503ddad6b8bc3777a54b5

RUN curl -fsSL -O https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    echo "${TERRAFORM_SHA256SUM}  terraform_${TERRAFORM_VERSION}_linux_amd64.zip" > terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    sha256sum -c terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/

CMD [ "terraform", "version" ]
