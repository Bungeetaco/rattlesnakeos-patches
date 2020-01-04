# rattlesnakeos-patches
Corrmaan patches for Rattlesnake OS. Forked for crosshatch.

## opengapps
Note that building opengapps with Rattlesnake OS will require a larger EC2 volume size. By default it's set to 200 GB, but can be increased by editing the value of the `VolumeSize` key in `templates/lambda_template.go`. 300 worked for me.

As well, opengapps' aosp_build requires `zlib`. Script to install it is available at https://github.com/corrmaan/rattlesnakeos-scripts.

Remember to add the following to your `~/.rattlesnakeos.toml` config file, following the instructions for the OpenGApps AOSP based build system (https://github.com/opengapps/aosp_build):

````toml
[[custom-patches]]
  repo = "https://github.com/Bungeetaco/rattlesnakeos-patches"
  patches = [
      "0001-magisk_mkbootfs.patch",
      "0002-opengapps-crosshatch.patch",
      "0003-enable-doze-mode.patch",
      "0004-opengapps-find-apk-for-pkg.patch",
  ]
  
[[custom-manifest-remotes]]
  name = "opengapps"
  fetch = "https://github.com/opengapps/"
  revision = "master"

[[custom-manifest-remotes]]
  name = "gitlab"
  fetch = "https://gitlab.opengapps.org/opengapps/"
  revision = "master"

[[custom-manifest-projects]]
  path = "vendor/opengapps/build"
  name = "aosp_build"
  remote = "opengapps"

[[custom-manifest-projects]]
  path = "vendor/opengapps/sources/all"
  name = "all"
  remote = "gitlab"

[[custom-manifest-projects]]
  path = "vendor/opengapps/sources/arm"
  name = "arm"
  remote = "gitlab"

[[custom-manifest-projects]]
  path = "vendor/opengapps/sources/arm64"
  name = "arm64"
  remote = "gitlab"

[[custom-manifest-projects]]
  path = "vendor/opengapps/sources/x86"
  name = "x86"
  remote = "gitlab"

[[custom-manifest-projects]]
  path = "vendor/opengapps/sources/x86_64"
  name = "x86_64"
  remote = "gitlab"
````

## Magisk
Please see CaseyBakey's work on including Magisk in the build. The `add_magisk()` function in their build script at https://github.com/CaseyBakey/chaosp/blob/master/build.sh should be added to `templates/build_template.go` and called after `build_aosp` and before `release "${DEVICE}"` in `full_run()`.
