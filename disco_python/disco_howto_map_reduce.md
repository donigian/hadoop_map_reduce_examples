
Prepare input data
Disco can distribute computation only as well as data can be distributed. In general, we can push data to Disco Distributed Filesystem, which will take care of distributing and replicating it.

ddfs chunk data:bigtxt ./bigfile.txt

ddfs blobs data:bigtxt

ddfs xcat data:bigtxt | less
