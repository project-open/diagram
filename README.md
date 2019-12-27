# OpenACS Diagram 
This package is part of ]project-open[, an open-source enterprise project management system.

For more information about ]project-open[ please see:
* [Documentation Wiki](http://www.project-open.com/en/)
* [V5.0 Download](https://sourceforge.net/projects/project-open/files/project-open/V5.0/)
* [Installation Instructions](http://www.project-open.com/en/list-installers)

About OpenACS Diagram :

<a href="mailto:nima.mazloumi@gmx.de">&shy;Nima Mazloumi</a><a href="mailto:lutz.tautenhahn@lutanho.net">Lutz Tautenhahn</a><p>This package extends the templating system of OpenACS by providing another builder next to the list and form builder. The diagram builder is very similar to the list builder. Two differences are important though: The multirow to be used must me defined bofore <a href="http://www.project-open.com/api-doc/proc-view?proc=template::diagram::create">template::diagram::create</a> is called since the column names are retrieved dynamically. <p> The diagram builder was developed in a way that it can be extended to use different engines for the rendering of the diagrams. Currently it is based on the &quot;Javascript Diagram Builder&quot;, v3.3 Lutz Tautenhahn. But other engines could be integrated in future like GNUPlot. <p>The rendering is taking place in the templates defined under resources/diagram/.. . Currently we support the following types: pie, curve and cockpit. You can customize the way they render the diagrams by editing the corresponding templates or adding new ones. Once a template is created you simply pass its name with the -template switch of <a href="http://www.project-open.com/api-doc/proc-view?proc=template::diagram::create">template::diagram::create</a>. <p><p>You need to run the <code>diagram-create.sql</code> to view the examples below. It will create a table with dummy data. You can remove the table again using <code>diagram-drop.sql</code>. <p>A detailed example is given in the API Browser. This page also contains examples for the three diagram types &quot;pie&quot;, &quot;curve&quot; and &quot;cockpit&quot;. As you can see the diagrams are beautifully inserted inside the page flow. Also CSV-Export is possible. <a class="button" href="index?csv=1">CSV</a><script language="javascript">
function MouseOver(i) { P[i].MoveTo("","",10); }
function MouseOut(i)  { P[i].MoveTo("","",0); }

</script><script language="javascript">
document.open();
v='8';
document.close();

</script><script language="javascript">
document.open();
v='8';
document.close();

</script><p><p><p><p><p><p><p><p>In order to make this builder easier to be extended the Javascript specific parts have to be removed: <ul><li>Affected are the procs: <code>template::diagram::prepare_value</code>, <code>template::diagram::update_borders</code> and <code>template::diagram::set_borders</code> which nead a clean up. Maybe moving these information into the templates would be best. <li>Date and Timestamp based values from the database have to be formatted in a special way. You must use <code>to_char(mydate, &#39;YYYY,MM,DD[,HH24][,MI][,SS]&#39;)</code> in your sql query to return a meaningful value. As you can see some elements are optional. For details please view the <code>Date</code> and <code>UTC</code> objects documentation for JavaScript. </ul><p><p>Not everything available in the Javascript Diagram Builder was fully integrated. There are many other things that could be done in future as well. Here some ideas: <ul><li>Give support for GNUPlot - a very powerful engine that has support for all diagram types including world maps... <li>Allow the definition of scales. Currently a developer would need to touch the Javascript Library to add new scales types <li>Add another package depeding on diagrams and portals and allows the definition of a repository of monitors and associate them with a role. Thus a given user could select from a extensible list of diagrams and define a user-specific report page. This would extend OpenACS towards real business intelligence toolkit for companies, universities and research labs. It would be important though to extend diagram to use from a pool of data sources like: databases, tcl scripts, remove web services... <li>Provide an XoTCL version in order to support different classes of diagrams and to improve reusablity. </ul><p>

# Online Reference Documentation

## Introduction Diagram v0.2b



## Extending the Diagram Builder



## Examples

<table align="left" cellpadding="3" cellspacing="1"><tbody><tr><td></td><td valign="top"> Legend </td></tr></tbody></table>

## Limitations



## Future Work



