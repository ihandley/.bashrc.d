# Load files into .bash_profile
#!/bin/bash

# https://github.com/koalaman/shellcheck/wiki/SC2044
shopt -s globstar nullglob
for file in ~/.bashrc.d/src/**/*.bashrc
do
  source "$file"
done

# Give files correct permissions
chmod -R 700 ~/.bashrc.d
find ~/.bashrc.d/src -name '*.bashrc' | xargs chmod +x
