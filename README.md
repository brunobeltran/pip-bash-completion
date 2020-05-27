Pip Bash Completion
===================

Bash autocompletion for [pip](https://github.com/pypa/pip). Understands
virtualenvs and can autocomplete package names from PyPI *fast*.


## Installation

Requires that [`pip-cache`](https://github.com/brunobeltran/pip-cache) be installed:

    $ pip install pip-cache

Global:

    $ git clone git://github.com/brunobeltran/pip-bash-completion.git
    $ sudo cp ./pip-bash-completion/pip /etc/bash_completion.d/
    $ . /etc/bash_completion.d/pip


Local:

    $ mkdir ~/.bash_completion.d
    $ cp ./pip-bash-completion/pip ~/.bash_completion.d/
    $ cat >> ~/.bashrc << EOM
    >
    > if [ -f ~/.bash_completion.d/pip ] ; then
    >     . ~/.bash_completion.d/pip
    > fi
    > EOM
    $ . ~/.bash_completion.d/pip


## Usage

(Optionally) update your local index of PyPI *a la* `apt-get update` via
`pip-cache` (does NOT require root):

    $ pip-cache update
    Connecting to PyPi...downloading package names...done!
    Writing packages to cache...done!

To list pip's commands:

    $ pip [TAB]
    bundle     freeze     help       install    search     uninstall  unzip      zip


To complete command:

    $ pip i[TAB]
    $ pip install


To list pip's options for commands:

    $ pip install -[TAB][TAB]
    --allow-all-external         --egg                        --no-binary                  --root
    --allow-external             --exists-action              --no-cache-dir               --src
    --allow-unverified           --extra-index-url            --no-clean                   -t
    -b                           -f                           --no-compile                 --target
    --build                      --find-links                 --no-deps                    --timeout
    -c                           --force-reinstall            --no-index                   --trusted-host
    --cache-dir                  --global-option              --no-use-wheel               -U
    --cert                       -h                           --only-binary                --upgrade
    --client-cert                --help                       --pre                        --user
    --compile                    -i                           --process-dependency-links   -v
    --constraint                 -I                           --proxy                      -V
    -d                           --ignore-installed           -q,                          --verbose
    --disable-pip-version-check  --index-url                  --quiet                      --version
    --download                   --install-option             -r
    -e                           --isolated                   --requirement
    --editable                   --log                        --retries


To dynamically query available packages (example from my system, your output
will depend on what packages you have installed):

    $ pip uninstall b[TAB][TAB]
    backports-abc   beautifulsoup4  billiard

or

    $ pip install pip-[TAB][TAB]
    pip-accel             pip-conflict-checker  pip-for-Windows       pip-prometheus        pip-tools-win
    pip-autoremove        pip-crate             pip-gun               pip-review            pip-uninstall
    pip-bundle            pip-create            pip-init              pip-tools             pip-upgrade
    pip-cache             pip-faster            pip-pop               pip-tools-optimizely  pip-Win

## Links

Another good autocompleter for `pip` that can't autocomplete package names and is significantly slower but does not require that an external python package be installed can be found [here](https://github.com/ekalinin/pip-bash-completion).
