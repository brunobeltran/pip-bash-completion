Pip Bash Completion
===================

Bash autocompletion for [pip](https://github.com/pypa/pip). Understands
virtualenvs and can autocomplete package names from PyPi *fast*.


## Installation

Global:

    $ sudo pip install pip-cache
    $ git clone git://github.com/brunobeltran/pip-bash-completion.git
    $ sudo cp ./pip-bash-completion/pip /etc/bash_completion.d/
    $ . /etc/bash_completion.d/pip


Local:

    $ pip install pip-cache
    $ mkdir ~/bash_completion.d
    $ cp ./pip-bash-completion/pip ~/bash_completion.d/
    $ echo "" >> ~/.bashrc
    $ echo 'if [ -f "$HOME/bash_completion.d/pip" ] ; then' >> ~/.bashrc
    $ echo '    . $HOME/bash_completion.d/pip' >> ~/.bashrc
    $ echo "fi" >> ~/.bashrc
    $ . ~/bash_completion.d/pip


## Usage


To list pip's commands:

    $ pip [TAB]
    bundle     freeze     help       install    search     uninstall  unzip      zip


To complete command:

    $ pip i[TAB]
    $ pip install


To list pip's options for commands:

    $ pip install -[TAB][TAB]
    -b                     --download-cache=      -f                     -I                     --mirrors=             --pypi-url=            --source-directory=    --user
    --build=               --download-dir=        --find-links           --ignore-installed     --no-dependencies      -q                     --src=                 -v
    --build-dir=           --download-directory=  --find-links=          --index-url            --no-deps              --quiet                -t                     --verbose
    --build-directory=     -e                     --force-reinstall      --index-url=           --no-download          -r                     --target=              --version
    -c                     --editable             --global-option=       --install-             --no-index             --requirement=         --timeout=
    -d                     --editable=            -h                     --install-option=      --no-install           -s                     -U
    --default-timeout=     --exists-action=       --help                 --log=                 -p                     --source=              --upgrade
    --download=            --extra-index-url=     -i                     -M                     --proxy=               --source-dir=          --use-mirrors

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

A good autocompleter for `pip` that can't autocomplete package names and is significantly slower but does not require an external python package to be installed can be found [here](https://github.com/ekalinin/pip-bash-completion).
