---
layout: post
title:  "DSpace XMLUI - Character Encoding Bug"
date:   2019-01-05 13:33:00
categories: DSpace
---

# Bug in Google Scholar tags

DSpace exposes metadata in the HTML HEAD section of item pages, to make it easier for Google Scholar to index the (scientific) publications. We were recently informed of a problem in case there are special characters in author names. For example in [this test item](http://demo.dspace.org/xmlui/handle/10673/314), if you right click and do "view source", you can see that unwanted escaping is added in the author name with special characters:

```
<meta content="&egrave;t&eacute;stein&icirc;" name="citation_author">
```

should be just regular UTF-8 encoded:

```
<meta content="ètésteinî" name="citation_author">
```

See if I can fix this ...

# Trying to build my local DSpace 6

It has been ages since I did a local build of DSpace 6. When trying it again, I was confronted with:

```
[ERROR] Failed to execute goal on project dspace-api: Could not resolve dependencies for project org.dspace:dspace-api:jar:6.4-SNAPSHOT: Failed to collect dependencies at org.postgresql:postgresql:jar:42.2.1.jre7: Failed to read artifact descriptor for org.postgresql:postgresql:jar:42.2.1.jre7: Could not transfer artifact org.postgresql:postgresql:pom:42.2.1.jre7 from/to central (https://repo.maven.apache.org/maven2): Received fatal alert: protocol_version -> [Help 1]
```

[Why am I getting “Received fatal alert: protocol_version” or “peer not authenticated” from Maven Central?](https://stackoverflow.com/questions/50824789/why-am-i-getting-received-fatal-alert-protocol-version-or-peer-not-authentic) brought help.

Adding -Dhttps.protocols=TLSv1.2 to my mvn build commands did the trick.

# Disable output escaping

For the non-citation_ tags, they are already assembled in one block in the DRI and then put into the page with this XSL instruction:

```
<xsl:if test="/dri:document/dri:meta/dri:pageMeta/dri:metadata[@element='xhtml_head_item']">
                <xsl:value-of select="/dri:document/dri:meta/dri:pageMeta/dri:metadata[@element='xhtml_head_item']"
                              disable-output-escaping="yes"/>
</xsl:if>
```

So from the problematic:

```
<!-- Add all Google Scholar Metadata values -->
            <xsl:for-each select="/dri:document/dri:meta/dri:pageMeta/dri:metadata[substring(@element, 1, 9) = 'citation_']">
                <meta name="{@element}" content="{.}"></meta>
            </xsl:for-each>
```

I tried to go to:

```
<xsl:for-each select="/dri:document/dri:meta/dri:pageMeta/dri:metadata[substring(@element, 1, 9) = 'citation_']" >
                <meta name="{@element}">
                    <xsl:attribute name="content">
                        <xsl:value-of select="." disable-output-escaping="yes" />
                    </xsl:attribute>
                </meta>
            </xsl:for-each>
```

Only to learn that [output escaping doesn't seem to be possible for attributes](https://stackoverflow.com/questions/7887016/disable-output-escaping-not-working-for-attribute-in-xslt).

[XSL - How to disable output escaping for an attribute?](https://stackoverflow.com/questions/2921123/xsl-how-to-disable-output-escaping-for-an-attribute) showed an approach where the entire tag could be
written as text. Not pretty but it got the job done.

Ticket: https://jira.duraspace.org/browse/DS-4135
Pull Request: https://github.com/DSpace/DSpace/pull/2317