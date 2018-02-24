# flowable-userguide
Flowable userguide and translate into Chinese.


_ORIGINAL README BELOW_


About
-------

This project regroup all userguide informations.

Currently it contains :

* [BPMN](/src/en/bpmn) : Business Process Management Notation User Guide
* [CMMN](/src/en/cmmn) : Case Management Model Notation User Guide
* [DMN](/src/en/dmn) : Decision Model and Notation User Guide
* [FORM](/src/en/form) : Form engine User Guide
* [SINGLE (Beta Version)](/src/en/single) : Unified version of all previous documentation

Tooling
-------

Install Asciidoctor: http://asciidoctor.org/

We're using the 'pygments' library for syntax highlighting. This needs to be installed on your system too: 
```ruby 
gem install pygments.rb 
```


Generating the docs
--------------------

**Using build.xml**

Simply select run the *build.docs.[bpmn|cmmn|dmn|form|single|all]* goal and it will generates both html & pdf version.
All generated files will be available in root project **target** folder.


**From scripts folder**

Go to the [scripts Folder](/scripts)
* Call the generate-all.sh [bpmn|cmmn|dmn|form|single] to generate for a single project both html & pdf version
```bash 
# Genate BPMN documentation in html & pdf format
> ./generate-all.sh bpmn
```
* Call the generate-html.sh [bpmn|cmmn|dmn|form|single] to generate html
```bash 
# Genate Form documentation in html format
> ./generate-html.sh form
```
* Call the generate-pdf.sh [bpmn|cmmn|dmn|form|single] to generate pdf
```bash 
# Genate DMN documentation in pdf format
> ./generate-pdf.sh dmn
```

**From each project folder**

Use **./generate-html.sh** for html only and likewise **./generate-pdf.sh** for pdf only.


Docs on the docs
----------------

The html is generated using the **'index-html.adoc'** file per project. The pdf generation uses the **'index-pdf.adoc'** file per project. Both reference a shared **'index-common.adoc'** file for the actual content, but define different parameters in the preamble.

When building the html doc, following files get included automatically:

* **base/flowable.css** : this is the stylesheet for the docs. The css will be included inline in the html docs.
* **base/docinfo.html** : this file gets included at the top of the html file. It contains the tocbot library and a little script to initialize the dynamic table of contents.


NB
-------
We still use Ant as building tool because Asciidoctor Maven Plugin doesn't support the current level of quality for the generated documenation. We "still" have to use asciidoc command line.



