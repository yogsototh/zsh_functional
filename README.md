# ZSH higher order functions


You can look at [this article<sup>†</sup>](http://yannesposito.com/Scratch/en/blog/Higher-order-function-in-zsh/) to have more informations.

To install just clone it to `~/.zsh/functional` 

    mkdir ~/.zsh
    git clone https://yogsototh@github.com/yogsototh/zsh_functional.git ~/.zsh/functional

and add

    # Load functions
    func_reps=( ~/.zsh/functional/src )
    for rep in $func_reps; do
        fpath=($rep $fpath)
        autoload -U $rep/*(:t)
    done

to your `.zshrc`
