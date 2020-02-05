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
  ]
````
