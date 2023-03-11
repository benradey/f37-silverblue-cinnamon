FROM ghcr.io/benradey/f37-cinnamon-base:latest

RUN rpm-ostree install \
  akmod-nvidia \
  libva-utils \
  nvidia-vaapi-driver \
  radeontop \
  solaar \
  vdpauinfo \
  xorg-x11-drv-nvidia \
  xorg-x11-drv-nvidia-cuda \
  xorg-x11-drv-nvidia-cuda-libs



# CREDIT for the below goes to twiest: https://github.com/twiest/silverblue-images/tree/main/silverblue-shuttle-sz170r8v2

RUN mkdir -p /var/log/akmods /var/tmp /run/akmods \
&& chmod --reference=/tmp /var/tmp

# TODO: Remove the following line once this bug is fixed: https://github.com/coreos/rpm-ostree/issues/4201
RUN [ -f /usr/bin/ld ] || ln -s /usr/bin/ld.bfd /usr/bin/ld

RUN echo "rpm-ostree install \"\$4\"" | tee /usr/bin/dnf && chmod +x /usr/bin/dnf \
&& /usr/sbin/akmods --force --kernels "$(rpm -qa kernel --queryformat '%{VERSION}-%{RELEASE}.%{ARCH}')"

# TODO: Remove the following line once this bug is fixed: https://github.com/coreos/rpm-ostree/issues/4201
RUN [ -h /usr/bin/ld ] && rm /usr/bin/ld



RUN rm -rf /var /run/akmods /usr/bin/dnf \
&& ostree container commit
