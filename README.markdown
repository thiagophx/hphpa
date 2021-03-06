hphpa
=====

**hphpa** is a convenience wrapper for [HipHop](http://github.com/facebook/hiphop-php/)'s static analyzer.

Installation
------------

`hphpa` should be installed using the PEAR Installer, the backbone of the [PHP Extension and Application Repository](http://pear.php.net/) that provides a distribution system for PHP packages.

Depending on your OS distribution and/or your PHP environment, you may need to install PEAR or update your existing PEAR installation before you can proceed with the following instructions. `sudo pear upgrade PEAR` usually suffices to upgrade an existing PEAR installation. The [PEAR Manual ](http://pear.php.net/manual/en/installation.getting.php) explains how to perform a fresh installation of PEAR.

The following two commands (which you may have to run as `root`) are all that is required to install `hphpa` using the PEAR Installer:

    pear config-set auto_discover 1
    pear install pear.phpunit.de/hphpa

After the installation you can find the `hphpa` source files inside your local PEAR directory; the path is usually `/usr/lib/php/SebastianBergmann/HPHPA`.

Usage Example
-------------

    ➜  ~  hphpa --checkstyle hphpa.xml /usr/local/src/code-coverage/PHP
    hphpa 1.1.0 by Sebastian Bergmann.

    Using ruleset /usr/share/pear/data/hphpa/ruleset.xml

    /usr/local/src/code-coverage/PHP/CodeCoverage/Filter.php
      206   Too many arguments in function or method call:
            $this->addFileToWhitelist($file, FALSE)

    Found 1 violation in 1 file (out of 21 total files).

    ➜  ~  cat hphpa.xml
    <?xml version="1.0" encoding="UTF-8"?>
    <checkstyle>
     <file name="/usr/local/src/code-coverage/PHP/CodeCoverage/Filter.php">
      <error line="206"
             message="Too many arguments in function or method call:
                      $this-&gt;addFileToWhitelist($file, FALSE)"
             source="HipHop.PHP.Analysis.TooManyArgument"
             severity="error"/>
     </file>
    </checkstyle>
