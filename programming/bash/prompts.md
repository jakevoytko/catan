# Prompting in Bash

## Yes/no prompts

```bash
read -p "This permanently destroys all local data. Are you sure? " -n 1 -r
if [[ $REPLY =~ ^[Yy]$ ]]
then
  do_something
fi
```
