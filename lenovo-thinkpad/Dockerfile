FROM ghcr.io/benradey/f37-common-extras:latest

RUN rpm-ostree install \
  intel-media-driver \
&& rm -rf /var \
&& ostree container commit
