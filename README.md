# XML
XML language definition files

Export from 1.0.0 master sheet September 2015

# FILE NAME STRUCTURE
Every XML file has the following file name structure:

Polyglot-$version_$language[_$anotherLanguage].xml

- POLYGLOT is the name of the project
- VERSION is the version string (3 digits, no point or comma), e.g. "100"
- LANGUAGE is the ISO-639-1 language code (lower case) and the regional code (upper case), e.g. "enUS"

Version has a "-" (minus) in front, and all languages are separated by "_" (underscores) for easy string explosion.

# INTERNAL XML STRUCTURE
Every XML language file has the following structure:

<pre>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;resources&gt;
   &lt;polyglot LANG=$langstring DIRECTION=$direction VERSION=$version DATE=$date /&gt;
   &lt;s n=$idString&gt;$translation&lt;/s&gt;
   ...
&lt;/resources&gt;
</pre>

Explanation:
- XML 1.0 UTF-8 header
- "resources" root element
- "polyglot" info tag & attributes: $langstring (e.g. "German"), $direction ("ltr"/"rtl"), $version (e.g. "100"), $date (e.g. "2015-09-26")
- string tag "s" with name ID attribute "n"=$idString and $translation from the Polyglot database
- "resources" end tag
