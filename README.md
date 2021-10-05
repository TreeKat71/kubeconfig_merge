# kubeconfig_merge
Auto detect your kubeconfig files under specific folder with specified prefix and merge them.


# How to use
1. Put these lines in your ~/.bashrc or ~/.zshrc

        for k_cfg_path in $(find ~/.kube  -name 'config*' -type f)
        do
          k_cfg_list=$k_cfg_list:$k_cfg_path
        done
        export KUBECONFIG=$k_cfg_list

Then kubectl will load all kubeconfig files with `config` prefix under folder `~/.kube`.

2. Rename all the kubeconfig files want to be loaded with the prefix `config`.

For example, `config_1`, `config_taiwan`, etc...
<br>The paths will be like `~/.kube/config_1`, `~/.kube/config_taiwan`, `~/.kube/config_us`, etc... 


# Customized
If you are familiar with `find` command, then you can change the `args` to fit your need.
