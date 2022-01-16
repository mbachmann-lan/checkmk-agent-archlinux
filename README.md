# Checkmk Agent for Arch Linux

forked from: https://github.com/pfeilmann/check_mk-agent

list installed external packages
```
$ pacman -Qm
```

install package
```
$ pacman -U check-mk-agent-2.0.0p17-1-x86_64.pkg.tar.zst
```

remove package
```
$ pacman -R check-mk-agent      # package only
$ pacman -Rs check-mk-agent     # package with dependencies
$ pacman -Rns check-mk-agent    # package with dependencies and configuration files
```

For more information, please visit my [project homepage](https:#).
