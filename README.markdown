hphpa
=====

**hphpa** is a convenience wrapper for [HipHop](http://github.com/facebook/hiphop-php/)'s static analyzer.

Installation
------------

`hphpa` should be installed using the PEAR Installer, the backbone of the [PHP Extension and Application Repository](http://pear.php.net/) that provides a distribution system for PHP packages.

Depending on your OS distribution and/or your PHP environment, you may need to install PEAR or update your existing PEAR installation before you can proceed with the following instructions. `sudo pear upgrade PEAR` usually suffices to upgrade an existing PEAR installation. The [PEAR Manual ](http://pear.php.net/manual/en/installation.getting.php) explains how to perform a fresh installation of PEAR.

The following two commands (which you may have to run as `root`) are all that is required to install PHPUnit using the PEAR Installer:

    pear config-set auto_discover 1
    pear install pear.phpunit.de/hphpa

After the installation you can find the `hphpa` source files inside your local PEAR directory; the path is usually `/usr/lib/php/HPHPA`.

Usage Example
-------------

    ➜  ~  hphpa --checkstyle hphp.xml /usr/local/src/code-coverage/PHP
    hphpa 1.0.0 by Sebastian Bergmann.

    /usr/local/src/code-coverage/PHP/CodeCoverage/Filter.php
      206   TooManyArgument: $this->addFileToWhitelist($file, FALSE)

    ➜  ~  cat hphp.xml
    <checkstyle>
     <file name="/usr/local/src/code-coverage/PHP/CodeCoverage/Filter.php">
      <error line="206"
             message="TooManyArgument $this-&gt;addFileToWhitelist($file, FALSE)"
             source="HipHop.PHP.Analysis.TooManyArgument"
             severity="error"/>
     </file>
    </checkstyle>
