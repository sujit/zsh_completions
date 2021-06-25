Enabling Zsh auto-completions system
----------------------------------------------

1. Navigate to the following directory

    ```bash
    cd ~/.oh-my-zsh
    mkdir completions # Run only if folder non-existent
    ```

2. Add the following line to your ~.zshrc

    ```bash
    autoload -Uz compinit && compinit
    ```

3. An example for ripgrep:

    ```bash
    # Download the desired package
    $wget 'https://github.com/BurntSushi/ripgrep/releases/download/13.0.0/ripgrep-13.0.0-x86_64-unknown-linux-musl.tar.gz'
    tar -zxvf ripgrep-13.0.0-x86_64-unknown-linux-musl.tar.gz

    # Navigate to the extracted directory
    $cd ripgrep-13.0.0-x86_64-unknown-linux-musl

    # Copy ripgrep (rg) completion script
    $cp complete/_rg ~/.oh-my-zsh/completions/

    # Reload Zsh
    $exec zsh

    # See the completion into action :)
    $rg --<tab>
    ```

**NOTE:** *For obvious reasons, you need to have the ripgrep binary installed to your system path.*


Force a rebuild (if required)
----------------------------------------------

    ```
    $rm -f ~/.zcompdump
    compinit
    ```

Enable case-insensitive path/tab completion
----------------------------------------------

    ```code
    zstyle ':completion:*' matcher-list 'm:{[:lower:][:upper:]}={[:upper:][:lower:]}' 'm:{[:lower:][:upper:]}={[:upper:][:lower:]} l:|=* r:|=*' 'm:{[:lower:][:upper:]}={[:upper:][:lower:]} l:|=* r:|=*' 'm:{[:lower:][:upper:]}={[:upper:][:lower:]} l:|=* r:|=*'
    ```

References
------------------------
* [zsh completions](https://scriptingosx.com/2019/07/moving-to-zsh-part-5-completions/)
* [how to write zsh completion scripts](https://mads-hartmann.com/2017/08/06/writing-zsh-completion-scripts.html)
