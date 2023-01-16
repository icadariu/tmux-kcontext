# Tmux Kube context

* The goal of this repository is to have a Tmux plugin that display current kube context & namespace based on the active Tmux pane/window.
* It doesn't matter if user uses a single .kube/config or multiple and uses `KUBECONFIG` to point to the correct config, it should not error.
* Even if there are alternatives, I wanted to give it a try and see how I would do it.

## Why this repository

* Mostly educational purpose. I want to "play" with:
  * Creating a tmux plugin that is also useful in my setup (tmux + kube contexts)
  * GitHub Projects
  * Issues linked to projects
  * ISSUE_TEMPLATE
  * Having fun learning new stuff!

## Milestones

1. Functional shell script

* Script can:
 * Fetch current kube context based on KUBECONFIG (or any other option)
 * Fetch current namespace
 * Doesn't error in case there is no context defined, but, maybe, throw error
 * Output context + namespace in colors (useful later in tmux)
   ```console
   # from kube-tmux
   # [fg=blue]⎈ #[fg=colour]#[fg=]kind-kind#[fg=colour250]:#[fg=]default
   ```

* Tests:
  * Running multiple times gives the same result as long as `export KUBCONFIG` stays the same.
  * Switching to a different pane will not trigger an error in case there is no KUBECONFIG
    * If KUBECONFIG is defined, display that new context + namespace

2. Release

* Checks:
  * no Markdown lint issues
  * no grammar issues
  * close bugs
  * test functionality
* something similar to

* Release:
  * create the tmux plugin
  * release version

3. Improvements

* When creating a new pane, make sure to keep last context active in this newly created pane.

## Credits

* This project was inspired by:
  * <https://github.com/jonmosco/kube-tmux>
  * <https://github.com/thecasualcoder/kube-tmuxp>
  * <https://github.com/uesyn/tmux-kubecontext>
  * <https://github.com/kr3cj/tmux-kube>

