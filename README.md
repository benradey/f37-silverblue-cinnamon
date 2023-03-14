# f37-silverblue-cinnamon
An attempt at an unofficial Cinnamon spin of Fedora Silverblue 37.

`sudo rpm-ostree rebase --experimental ostree-unverified-registry:ghcr.io/benradey/f37-lenovo-ideapad.latest` (for example)

Note that after rebasing into these images, the packages slick-greeter and slick-greeter-cinnamon will still need to be added manually. Attempting to roll them into the image somehow prevents slick-greeter and lightdm from connecting, resulting in the lightdm service failing to start.

1. `sudo rpm-ostree install slick-greeter slick-greeter-cinnamon`
2. `sudo systemctl disable display-manager && sudo systemctl enable lightdm` (lightdm appears to be installed in the base image, even though gdm is used by default)
