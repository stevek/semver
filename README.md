SemVer2 3.3.x gem, following semver.org 2.0.0-rc.2
======

quickstart on the command line
------------------------------
install it

    % gem install semver2

use it

    % semver                    # => v2.3.4
    Find the .semver file and print a formatted string from this.

    % semver init
    Initialize the .semver file.

    % semver tag                # => v0.0.0
    Print the tag for the current .semver file.

    % semver inc minor          # => v0.1.0
    % semver pre 'alpha.45'     # => v0.1.0-alpha.45
    % semver meta 'md5.abc123'  # => v0.1.0-alpha.45+md5.abc123
    % semver format "%M.%m"     # => 0.1
    % git tag -a `semver tag`
    % say 'that was easy'

quickstart for ruby
-------------------

    require 'semver'
    v = SemVer.find
    v.major                     # => "0"
    v.major += 1
    v.major                     # => "1"
    v.prerelease = 'alpha.46'
    v.metadata = 'md5.abc123'
    v.format "%M.%m.%p%s%d"     # => "1.1.0-alpha.46+md5.abc123"
    v.to_s                      # => "v1.1.0-alpha.46+md5.abc123"
    v.save


git integration
---------------
    % git config --global alias.semtag '!git tag -a $(semver tag) -m "tagging $(semver tag)"'


existing 'SemVer' class from other gem?
---------------------------------------
You can now do this:

    require 'xsemver'
    v = XSemVer::SemVer.find
    # ...
    v.save

creds
-----
* [Franco Lazzarino](mailto:flazzarino@gmail.com)
* [Henrik Feldt](mailto:henrik@haf.se)
* [James Childress](mailto:james@childr.es)
