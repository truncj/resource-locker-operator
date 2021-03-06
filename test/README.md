# Tests

Execute the following:

```shell
oc new-project resource-locker-test
oc adm policy add-role-to-user admin -z default -n resource-locker-test
oc apply -f ./test/resource_test.yaml -n resource-locker-test
```

```shell
oc create sa test -n resource-locker-test
oc apply -f ./test/simple_patch.yaml -n resource-locker-test
```

```shell
oc adm policy add-role-to-user view system:serviceaccount:resource-locker-test:default -n default
oc apply -f ./test/complex_patch.yaml -n resource-locker-test
```

```shell
oc apply -f ./test/field_patch.yaml -n resource-locker-test
```

```shell
oc apply -f ./test/combined.yaml
```
