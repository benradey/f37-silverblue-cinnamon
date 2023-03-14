FROM ghcr.io/benradey/f37-cinnamon-base:latest

RUN rpm-ostree install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

RUN rpm-ostree override remove \
  ffmpeg-free \
  firefox \
  firefox-langpacks \
  libavcodec-free \
  libavdevice-free \
  libavfilter-free \
  libavformat-free \
  libavutil-free \
  libpostproc-free \
  libswresample-free \
  libswscale-free \
  mesa-va-drivers \
  mpv \
&& rpm-ostree install \
  cheese \
  ffmpeg \
  egl-utils \
  libva-utils \
  mesa-va-drivers-freeworld \
  mpv \
  solaar \
  sshfs \
  vim \
&& rm -rf /var \
&& ostree container commit
