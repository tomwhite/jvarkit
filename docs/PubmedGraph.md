# PubmedGraph

![Last commit](https://img.shields.io/github/last-commit/lindenb/jvarkit.png)

Creates a Gephi-gexf graph of references-cites for a given PMID


## Usage

```
Usage: pubmedgraph [options] Files
  Options:
    -h, --help
      print help and exit
    --helpFormat
      What kind of help. One of [usage,markdown,xml].
    --ncbi-api-key
      NCBI API Key see https://ncbiinsights.ncbi.nlm.nih.gov/2017/11/02/new-api-keys-for-the-e-utilities/ 
      .If undefined, it will try to get in that order:  1) environment 
      variable ${NCBI_API_KEY} ;  2) the jvm property "ncbi.api.key" ;	3) A 
      java property file ${HOME}/.ncbi.properties and key api_key
    -o, --output
      Output file. Optional . Default: stdout
    --version
      print version and exit
    -b
      disable backward (referenced-in)
      Default: false
    -d
      max-depth
      Default: 3
    -f
      disable forward (cited-in)
      Default: false

```


## Keywords

 * pubmed
 * xml
 * graph


## Compilation

### Requirements / Dependencies

* java [compiler SDK 11](https://jdk.java.net/11/). Please check that this java is in the `${PATH}`. Setting JAVA_HOME is not enough : (e.g: https://github.com/lindenb/jvarkit/issues/23 )


### Download and Compile

```bash
$ git clone "https://github.com/lindenb/jvarkit.git"
$ cd jvarkit
$ ./gradlew pubmedgraph
```

The java jar file will be installed in the `dist` directory.

## Source code 

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/pubmed/PubmedGraph.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/pubmed/PubmedGraph.java)


## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **pubmedgraph** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)



## Example

```
$ java -jar dist/pubmedgraph.jar -d 0 15047801 
```


```
<?xml version="1.0" encoding="UTF-8"?>
<gexf xmlns="http://www.gexf.net/1.3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.gexf.net/1.3 http://www.gexf.net/1.3/gexf.xsd" version="1.3">
  <meta>
    <creator>PubmedGraph  by Pierre Lindenbaum</creator>
    <description/>
  </meta>
  <graph mode="static" defaultedgetype="directed">
    <attributes class="node" mode="static"/>
    <attributes class="edge" mode="static">
      <attribute id="0" title="pmid" type="string"/>
      <attribute id="1" title="title" type="string"/>
      <attribute id="2" title="pubdate" type="string"/>
    </attributes>
    <nodes>
      <node id="10889507" label="Cleavage of polypeptide cha...">
        <attvalues>
          <attvalue for="0" value="10889507"/>
          <attvalue for="1" value="Cleavage of polypeptide chain initiation factor eIF4GI during apoptosis in lymphoma cells: characterisation of an internal fragment generated by caspase-3-mediated cleavage."/>
          <attvalue for="2" value="2000 Jul"/>
        </attvalues>
      </node>
      <node id="9989501" label="The structure of the protei...">
        <attvalues>
          <attvalue for="0" value="9989501"/>
          <attvalue for="1" value="The structure of the protein phosphatase 2A PR65/A subunit reveals the conformation of its 15 tandemly repeated HEAT motifs."/>
          <attvalue for="2" value="1999 Jan 8"/>
        </attvalues>
      </node>
      <node id="11792322" label="Recognition of the rotaviru...">
        <attvalues>
          <attvalue for="0" value="11792322"/>
          <attvalue for="1" value="Recognition of the rotavirus mRNA 3' consensus by an asymmetric NSP3 homodimer."/>
          <attvalue for="2" value="2002 Jan 11"/>
        </attvalues>
      </node>
      <node id="11875511" label="How a rotavirus hijacks the...">
        <attvalues>
          <attvalue for="0" value="11875511"/>
```

