# kubeconfig_merge
Auto detect your kubeconfig files under specific folder with specified prefix and merge them.


# How to use
Put these lines in your ~/.bashrc or ~/.zshrc

    for k_cfg_path in $(find ~/.kube  -name 'config*' -type f)
    do
      k_cfg_list=$k_cfg_list:$k_cfg_path
    done
    export KUBECONFIG=$k_cfg_list

Then kubectl will load all kubeconfig files with `config` prefix under folder `~/.kube`.
<br>For example, `~/.kube/config_1`, `~/.kube/config_taiwan`, `~/.kube/config_us`, etc... 


You can change the `args` in your `find` command to fit your need.
