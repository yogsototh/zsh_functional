# ZSH higher order functions

You can look at [yogsototh's blogpost] for the idea of higher order functions
in zsh.

To install, clone this repo to `~/.zsh/functional` and add

    . ~/.zsh/functional/load

to your `.zshrc`

## Usage and documentation

Please refer to the tests so far until I've written simple proper docs for each
function. The function `map` and family will print out documentation for you
when calling them with no arguments.

Each of the method families, `map`, `each`, `filter` and `fold` are having a
"normal version" accompanied with lambda function version and a arithmetic
lambda version.

### Lambda functions

Use the versions ending with `l`, like `mapl`, `eachl`, `foldl`.

### Arithmetic lambda functions

Similarly, use the functions ending with `a`.

## Contributing

Good idea! Just add a test and implement the new functionality and send away
your pull request! :)

## Creds

Yann Esposito for the *HoF* idea and big thanks to [Sterling's blogpost] for
discovering and starting implementing the anonymous function features.

[yogsototh's blogpost]: http://yannesposito.com/Scratch/en/blog/Higher-order-function-in-zsh/
[Sterling's blogpost]:  http://nicholassterling.wordpress.com/2012/03/30/a-zsh-map-function/
