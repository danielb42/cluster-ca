# cluster-ca
Create a CA for your cluster apps (e.g. etcd, vault, ...)

Create the CA
-------------

```
./init-ca.sh <name_of_ca>
cd <name_of_ca>
./createCerts.sh server testsrv-1 testsrv-2 testsrv-3
./createCerts.sh client with-pfx crazy_einstein
./createCerts.sh multi my-etcd-cluster etcd-1 etcd-2 etcd-3

```
Done.

Use "server" followed by a list of hostnames to create multiple certs, one for every listed hostname.  
Use "multi" followed by the name of the cert and a list of hostnames to create a cert which contains the listed hosts in SAN.  
Use "client" followed by a username to create a user cert. Optionally precede name with `with-pfx` to generate a PFX file. 


