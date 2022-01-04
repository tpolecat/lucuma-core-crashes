# lucuma-core-crashes

These are crashes generated on clean builds of lucuma-core, which is haunted.

```bash
while (printf "\033c"; git clean -xdf; sbt compile); do :; done
```

Here are some crashes with

```
openjdk version "11.0.11" 2021-04-20
OpenJDK Runtime Environment GraalVM CE 21.1.0 (build 11.0.11+8-jvmci-21.1-b05)
OpenJDK 64-Bit Server VM GraalVM CE 21.1.0 (build 11.0.11+8-jvmci-21.1-b05, mixed mode, sharing)
```

| Variant | Count |
|--------|-------|
| 1      | 1     |
| 2      | 2     |
| 3      | 3     |
| 4      | 3     |
| 5      | 1     |

Now trying with

```
openjdk version "11.0.10" 2021-01-19 LTS
OpenJDK Runtime Environment Zulu11.45+27-CA (build 11.0.10+9-LTS)
OpenJDK 64-Bit Server VM Zulu11.45+27-CA (build 11.0.10+9-LTS, mixed mode)
```

| Variant | Count |
|--------|-------|
| 1      | 1     |
| 6      | 1     |

Ok this seems just as unstable after a few runs. Switching to

```
openjdk version "11.0.11" 2021-04-20
OpenJDK Runtime Environment AdoptOpenJDK-11.0.11+9 (build 11.0.11+9)
OpenJDK 64-Bit Server VM AdoptOpenJDK-11.0.11+9 (build 11.0.11+9, mixed mode)
```

| Variant | Count |
|--------|-------|
| 7      | 1     |
| 4      | 1     |

Ok I'm giving up on JVMs, it doens't seem to matter.

Now trying with 2.13.6

Nope, immediate crash.

How about 2.13.5?

`scalcOptions := Nil` doesn't fix things either. Blech.

