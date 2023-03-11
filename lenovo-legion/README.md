# f37-lenovo-legion

After rebasing to this image, the following command must be run to ensure that the `nvidia` driver is selected over the `nouveau` driver at boot:

`rpm-ostree kargs --append=rd.driver.blacklist=nouveau --append=modprobe.blacklist=nouveau --append=nvidia-drm.modeset=1 initcall_blacklist=simpledrm_platform_driver_init`

(Pulled from [RPM Fusion](https://rpmfusion.org/Howto/NVIDIA#OSTree_.28Silverblue.2FKinoite.2Fetc.29).)
