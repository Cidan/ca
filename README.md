## Wut?
A small set of wrappers for use at whisper to create a CA and certs, complete with revocation support, etc.

## Create CA

Run the following:

```
./create_ca
```

Which will make a `CA` directory in the current directory. This directory contains a complete CA, including serial number counters, revocation support, certificate storage, etc.

## Create Cert/Key Pair

After your CA is created, run:

```
./create_cert <name>
```

To create a cert with a Common Name set to `<name>`. The cert will be located in `CA/certs/<name>.crt` and the key in `CA/private/<name>.key`. The cert will be signed by the CA created above.

## Revoke Cert/Key Pair

To revoke a certificate, run:

```
./revoke_cert <name>
```

The certificate will be deleted, and entered into the revocation database in the CA.

## Starting Over

Simply delete the `CA` directory to delete all certs, CA, and databases, and re-run the `create_ca` script.

## TODO

Move more of the CA config into the openssl.cnf file.
