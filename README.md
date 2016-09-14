##Cloudant

######Cloudant is an IBM software product, which is primarily delivered as a cloud-based service. Cloudant is an open source non-relational, distributed database service of the same name that requires zero-configuration. Cloudant is based on the Apache-backed CouchDB project and the open source BigCouch project.

[More : CLOUDANT](https://en.wikipedia.org/wiki/Cloudant)

##PART 1: Primary Index

######The primary index is the fastest way to retrieve data from your database.

#### <li>Retrieving Data</li>
The primary index is fast because it comes with every Cloudant database.The primary index, often referred to as _all_docs, returns an id, a key and a value for every document in the database. The id and key are the same (Cloudant makes an index keyed by doc id), while the value is the _rev of the document.

`QUERY`
```C
https://[username].cloudant.com/animaldb/_all_docs
```

#### <li>Sort Order</li>
All indexes are sorted by their key. The sort order is:

<li>null
<li>false
<li>true
<li>numbers
<li>text, cases sensitive - lower case first
<li>arrays, sorted element by element
<li>objects
</li>

#### <li>Limit and Skip</li>
Add the limit parameter to keep your result set to a certain size. If you want to offset your result set you can also pass in a skip parameter.

```C
https://[username].cloudant.com/animaldb/_all_docs?limit=2&skip=3
```

#### <li>Slicing</li>
Use slicing to pull out row ranges from the index by using start and end keys in your query.

```C
https://[username].cloudant.com/animaldb/_all_docs?startkey="d"&endkey="giraffe"
```
