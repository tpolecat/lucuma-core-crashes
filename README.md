# lucuma-core-crashes

These are crashes generated on clean builds of lucuma-core, with

```
openjdk version "11.0.11" 2021-04-20
OpenJDK Runtime Environment GraalVM CE 21.1.0 (build 11.0.11+8-jvmci-21.1-b05)
OpenJDK 64-Bit Server VM GraalVM CE 21.1.0 (build 11.0.11+8-jvmci-21.1-b05, mixed mode, sharing)
```

via

```bash
while (printf "\033c"; git clean -xdf; sbt compile); do :; done
```

Summary

| Variant | Count | Comments |
|--------|-------|----------|
| 1      | 1     | `Bad superClass for class Any: <none>` |
| 2      | 2     | `Error while emitting ... assertion failed ... type ...` |
| 3      | 3     | `assertion failed: List(package shapeless, package shapeless)` |
| 4      | 1     | `an unexpected type representation reached the compiler backend` |