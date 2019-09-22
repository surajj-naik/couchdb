# Couchbase CouchDB (*github.com/couchbase/couchdb*)

**This is my personal checkout of the Couchbase CouchDB to modify and test experimental features and to work locally**

All the changes made here may or may not work with the official Couchbase build scripts and even if it builds may not behave as you expected.

***

I am trying to support Couchbase Collections in Couchbase/CouchDB. If successfull, there are few cool things you can do.

* CRUD views on collections within a scope rather than entire bucket.

* REST api for CRUD of views would include /<scope_name>/<collection_name> to ensure views are created on proper collections.

* Views on entire bucket will still be supported through default collections.

* View Index will be built for a particular collection.

* Upgrading from older version with view on buckets, will transform to views on default collections.

***

**Couchbase CouchDB is the codebase for the view engine of Couchbase. It is a mapreduce query and indexing engine. The mapreduce code is written in JavaScript (see the Couchbase docs). The map function emits keys, which becomes the nodes of the index tree and the reduce function is applied only to the leaf nodes. Unlike Hadoop Mapreduce, this is incremental in nature. The mapping and reducing is done only on the changed data.**

**Views as of now can only be created on buckets. I am trying to modify it to support Couchbase Collections, with which indexes can be built only on the collection of user's choice rather than the entire bucket resulting in faster index building if the data in collection is very small compared to entire bucket.**