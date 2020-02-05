# rattlesnakeos-patches
Patches for Rattlesnake OS. Forked for my personal crosshatch build.

Remember to add the following to your `~/.rattlesnakeos.toml` config file:

````toml
[[custom-patches]]
  repo = "https://github.com/Bungeetaco/ros-patches"
  patches = [
      "0001-round-icons.patch",
      "0002-increase-default-maximum-password-length.patch",
      "0003-Enable-WiFi-and-4G-calling.patch",
      "0004-disable-menu-entries-in-recovery.patch",
      "0005-do-not-require-strong-auth-on-regular-time-interval.patch",
      "0006-disable-agps.patch",
      "0007-set-cloudflare-dns-default.patch",
      "0008-increase-binder-proxy-counting-watermarks.patch",
      "0009-backup-any-app.patch",
      "0010-cosmetical-changes.patch",
      "0011-set-seedvault-as-dftl-bkp-provider.patch",
      "0012-internet-permission.patch",
  ]
````

You can also find my pre-builts for AuroraStore/AuroraDroid/AuroraServices/Seedvault @ https://gitlab.com/Bungeetaco/ros-prebuilts/
and my custom bootanimation over at https://github.com/Bungeetaco/ros-scripts
