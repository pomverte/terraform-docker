FROM python:3.8.7-alpine3.12

RUN apk add --no-cache --update \
    curl \
    git

ENV TERRAFORM_VERSION=0.14.3
ENV TERRAFORM_SHA256SUM=aa7b6cb6f366ffb920083b2a9739079ee560240ca31b580fe422af4af28cbb5a

RUN curl -fsSL -O https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    echo "${TERRAFORM_SHA256SUM}  terraform_${TERRAFORM_VERSION}_linux_amd64.zip" > terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    sha256sum -c terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/

CMD [ "terraform", "version" ]
