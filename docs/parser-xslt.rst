.. _xslt:

======================================================================
XSLT parser
======================================================================

:Maintainer: Masatake YAMATO <yamato@redhat.com>

This parser supports only version 1.0 of xslt syntax.
If newer version(2.0 and 3.0) is specified in an input file, ctags
just skips the input. With ``--verbose`` option, ctags prints how it
recognizes the version of input file.

scope information generated by xslt parser is a bit broken.  Currently
period(`.`) is used as separator in nested scopes. It is default value
of ctags.

This XSLT parser captures a node `<xsl:template match="...">` and the
value of `match` attribute is tagged with kind `matchedTemplate`.
When a `matchedTemplate` name is stored as part of scope information,
upper layer tools may be confused because `.` is used both as scope
separator and the match xpath expression.
