# registry

```sh
## manual push example

# export github token
export CR_PAT=<token>

# login to helm registry
echo $CR_PAT | helm registry login ghcr.io -u ajgrande924 --password-stdin

# build compressed chart tar file 
helm package -u -d .build console

# push as oci image
helm push ".build/console-x.x.x.tgz" oci://ghcr.io/ajgrande924/registry
```