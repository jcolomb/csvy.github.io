---
layout: index
---

### Welcome to CSVY.
This page describe the specs of yaml frontmatter for csv file format.
The main goals of the format are extreme simplicity and readability

Because for data human's curators from no-data, CSV, CSV+metadata to Semi-structured data, the technological gap is too large. A simple file format to add metadata to the existing datasets is needed, json is very cryptic for humans, but yaml can do the job.

For backward compatibility you can always add to your [data.csv](https://raw.githubusercontent.com/csvy/csvy.github.io/master/examples/data.csv) a [data.yml](https://raw.githubusercontent.com/csvy/csvy.github.io/master/examples/data.yml) metadata file, the next step when there is proper implementation make a single file [data.csvy](https://raw.githubusercontent.com/csvy/csvy.github.io/master/examples/data.csvy) will not be a problem at all.

There are many initiatives which it plans to use json + csv, but most are not meant to be published and read by humans.

### Defining table columns

Use the [JSON Table Schema](http://dataprotocols.org/json-table-schema/):

    ---
    name: my-dataset
    fields:
      - name: var1
        title: variable 1
        type: string
        description: explaining var1
        constraints:
          - required: true
      - name: var2
        title: variable 2
        type: integer
      - name: var3
        title: variable 3
        type: number
    ---
    var1,var2,var3
    A,1,2.5
    B,3,4.3

### Backwards Compatibility

Parser support for skipping multiple lines in the header (which would contain the YAML), and for comment lines (lines starting with `#`). Based on [CSV Parser Notes](https://github.com/hubgit/csvw/wiki/CSV-Parser-Notes) by [@hubgit](https://github.com/hubgit).

Language  | Parser     | Skip lines | Comment lines | Comments
----------| -----------| ---------- | ------------- | --------
Excel Mac |            | yes        | no            |
Python    | pandas     | yes        | yes           |
R         | read.table | yes        | yes           |
Ruby      | csv.read   | no         | yes           | skip lines via regex

### Related Projects

- [CSVW](http://www.w3.org/2013/csvw/wiki/Main_Page) (CSV on the Web)
- [Tabular Data Package](http://data.okfn.org/doc/tabular-data-package)
- [ARFF](https://weka.wikispaces.com/ARFF+(stable+version)) (Attribute-Relation File Format)

### Authors and Contributors

- [Javier Rovegno](https://github.com/jrovegno)
- [Martin Fenner](https://github.com/mfenner)

### Support or Contact

Use [Github Issues](https://github.com/csvy/csvy.github.io/issues).

### References

- [RFC4180](https://tools.ietf.org/html/rfc4180)
- [http://www.w3.org/TR/tabular-data-model/](http://www.w3.org/TR/tabular-data-model/)
- [http://jekyllrb.com/docs/frontmatter/](http://jekyllrb.com/docs/frontmatter/)
- [http://dataprotocols.org/json-table-schema/](http://dataprotocols.org/json-table-schema/)
- [http://dataprotocols.org/data-packages/](http://dataprotocols.org/data-packages/)
- [http://data.okfn.org/standards](http://data.okfn.org/standards)
- [http://data.okfn.org/doc/tabular-data-package](http://data.okfn.org/doc/tabular-data-package)
- [https://github.com/openspending/budget-data-package](https://github.com/openspending/budget-data-package)
- [http://data.okfn.org/tools/create](http://data.okfn.org/tools/create)
- [http://codebeautify.org/json-to-yaml](http://codebeautify.org/json-to-yaml)
- [http://codebeautify.org/yaml-to-json-xml-csv](http://codebeautify.org/yaml-to-json-xml-csv)
- [http://stackoverflow.com/questions/27838730/is-there-a-yaml-front-matter-standard-validator](http://stackoverflow.com/questions/27838730/is-there-a-yaml-front-matter-standard-validator)
- [Add YAML front matter block support for pandas.io.parsers.read_csv](https://github.com/pydata/pandas/issues/9613)
- [Allow custom metadata to be attached to panel/df/series](https://github.com/pydata/pandas/issues/2485)
- [Using YAML frontmatter with CSV](http://blog.datacite.org/using-yaml-frontmatter-with-csv/)
