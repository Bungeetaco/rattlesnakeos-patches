# rattlesnakeos-patches
Patches for Rattlesnake OS. Forked for my personal crosshatch build.

Remember to add the following to your `~/.rattlesnakeos.toml` config file:

````toml
[[custom-patches]]
  repo = "https://github.com/Bungeetaco/rattlesnakeos-patches"
  patches = [
      "0001-enable-doze-mode.patch",
  ]
````
