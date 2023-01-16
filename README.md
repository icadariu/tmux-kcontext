# Tmux Kube context

* The goal of this repository is to have a Tmux plugin that display current kube context & namespace based on the pane you work on in Tmux.
* It doesn't matter if user uses a single .kube/config or multiple and uses `KUBECONFIG` to point to the correct config.
* Even if there are alternatives, I wanted to give it a try and see how I would do it

## Milestones

1. Write the shell script that will fetch current kube context + namespace.

* Tests:
  * Running multiple times gives the same result as long as `export KUBCONFIG` stays the same.
  * Switching to a different pane will not trigger an error in case there is no KUBECONFIG
    * If KUBECONFIG is defined, display that new context + namespace

2. Output script with colors.

* something similar with

  ```console
  # from kube-tmux
  # [fg=blue]⎈ #[fg=colour]#[fg=]kind-kind#[fg=colour250]:#[fg=]default
  ```

3. Create the tmux plugin

## Credits

* This project was inspired by:
  * <https://github.com/jonmosco/kube-tmux>
  * <https://github.com/thecasualcoder/kube-tmuxp>
  * <https://github.com/uesyn/tmux-kubecontext>
  * <https://github.com/kr3cj/tmux-kube>
