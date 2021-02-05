# Build

## Command line vs config

`postcss-cli`accepts plugins via `--use`, but it's not as flexible since you can't
pass configuration via the command line. I'd recommend just having a postcss config file
when you start using it, because inevitably you'll use a plugin that requires configuration