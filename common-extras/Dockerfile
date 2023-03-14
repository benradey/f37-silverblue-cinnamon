FROM ghcr.io/benradey/f37-cinnamon-base:latest

RUN rpm-ostree install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

RUN rpm-ostree override remove \
  firefox \
  firefox-langpacks \
  mesa-va-drivers \
&& rpm-ostree install \
  cheese \
  ffmpeg \
  egl-utils \
  libva-utils \
  mesa-va-drivers-freeworld \
  solaar \
  sshfs \
  vim \
&& rm -rf /var \
&& ostree container commit
