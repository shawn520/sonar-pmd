# XPathRule
**Category:** `pmd`<br/>
**Rule Key:** `pmd:XPathRule`<br/>


-----

PMD provides a very handy method for creating new rules by writing an XPath query. When the XPath query finds a match, a violation is created.
Let's take a simple example: assume we have a Factory class that must be always declared final.
We'd like to report a violation each time a declaration of Factory is not declared final. Consider the following class:
<pre>
public class a {
  Factory f1;

  void myMethod() {
    Factory f2;
    int a;
  }
}
</pre>
The following expression does the magic we need:
<pre>
//VariableDeclarator
 [../Type/ReferenceType/ClassOrInterfaceType
  [@Image = 'Factory'] and ..[@Final='false']]
</pre>
See the <a href="http://pmd.sourceforge.net/xpathruletutorial.html" target="_blank">XPath rule
  tutorial</a> for more information.

<p>
  This rule is deprecated, please see the documentation on <a href="http://docs.sonarqube.org/x/HQxR" target="_blank">Extending
  Coding Rules</a>.
</p>
