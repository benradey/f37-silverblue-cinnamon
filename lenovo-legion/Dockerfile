FROM ghcr.io/benradey/f37-cinnamon-base:latest

RUN rpm-ostree install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
&& rpm-ostree install https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm \
&& rpm-ostree install \
  akmod-nvidia \
  solaar \
  xorg-x11-drv-nvidia \
&& rpm-ostree kargs --append=rd.driver.blacklist=nouveau --append=modprobe.blacklist=nouveau --append=nvidia-drm.modeset=1 initcall_blacklist=simpledrm_platform_driver_init \
&& rm -rf /var/* \
&& ostree container commit
