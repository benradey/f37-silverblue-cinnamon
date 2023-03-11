# f37-lenovo-legion

After rebasing to this image, the following command must be run to ensure that the `nvidia` driver is selected over the `nouveau` driver:

`rpm-ostree kargs --append=rd.driver.blacklist=nouveau --append=modprobe.blacklist=nouveau --append=nvidia-drm.modeset=1 initcall_blacklist=simpledrm_platform_driver_init`
