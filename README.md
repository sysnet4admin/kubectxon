# `kubectx` + `kubens`: Power tools for kubectl

![Latest GitHub release](https://img.shields.io/github/release/ahmetb/kubectx.svg)
![Proudly written in Bash](https://img.shields.io/badge/written%20in-bash-ff69b4.svg)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

**`kubectxon`** helps to avoid your mistake as show up active-context on the prompt:
![kubectxon-basic-demo GIF](img/kubectxon-basic-demo.gif)

**`kubectxon`** supports color variation on the prompt:
![kubectxon-color-demo GIF](img/kubectxon-color-demo.gif)

# kubectxon(1)

kubectxon is a utility to show up active-context.

```
USAGE:
  kubectx                   : list the contexts
  kubectx <NAME>            : switch to context <NAME>
  kubectx -                 : switch to the previous context
  kubectx -c, --current     : show the current context name
  kubectx <NEW_NAME>=<NAME> : rename context <NAME> to <NEW_NAME>
  kubectx <NEW_NAME>=.      : rename current-context to <NEW_NAME>
  kubectx -d <NAME>         : delete context <NAME> ('.' for current-context)
                              (this command won't delete the user/cluster entry
                              that is used by the context)
  kubectx -u, --unset       : unset the current context
```

### Usage

```bash
$ kubectl config get-contexts 
CURRENT   NAME     CLUSTER        AUTHINFO     NAMESPACE
*         beer     cluster-wk8s   wk8s-admin   
          bread    cluster-bk8s   bk8s-admin   
          coffee   cluster-hk8s   hk8s-admin 

$ kubectxon
Current state is "on"
$ (beer)

$ (beer) kubectxon
Current state is "off"
$ 
```

-----

## Installation
Caution: It support only 'BASH' Shell above 5.0.  
- As a `krew` which kubernetes plugins 
- Manual installation

### krew (under construction)
You can install and use [Krew](https://github.com/kubernetes-sigs/krew/) kubectl
plugin manager to get `kubectx` and `kubens`. **NOTE:** This will not install
shell completion scripts, if you want those, choose another installation method
below.

```bash
$ kubectl krew install ctxon 
```

After installing, the tools will be available as `kubectl ctxon`.


#### Manual

Since `kubectxon` is written in Bash, you should be able to install
them to any POSIX environment that has Bash installed.

- Download the `kubectxon` scripts.
- Either:
  - save them all to somewhere in your `PATH`,
  - or save them to a directory, then create symlinks to `kubectx`/`kubens` from
    somewhere in your `PATH`, like `/usr/local/bin`
- Make `kubectxon` executable (`chmod +x ...`)
  - For bash:
    ```bash
    $ git clone https://github.com/sysnet4admin/kubectxon.git
    $ cd kubectxon
    $ ./kubectxon
    ```
    OR
    ```bash
    $ curl -O https://raw.githubusercontent.com/sysnet4admin/kubectxon/main/kubectxon
    $ chmod +x kubectxon
    $ ./kubectxon
    ```

-----

### Uninstall kubectxon 
It supports auto-remover function. 

**`kubectxon`** supports to uninstaller:
![kubectxon-uninstall-demo GIF](img/kubectxon-uninstall-demo.gif)
