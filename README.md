# ioslog

bash script to use cfgutil syslog and get log information

## installation

```
curl -o <path>/ioslog \
     https://raw.githubusercontent.com/popmedic/bash-ioslog/master/ioslog && \
     chmod guo+x <path>/ioslog
```

## usage

```
<idx=[device index]> ioslog <pcregrep arguments>
```

where:
- &lt;idx=[device index]&gt; : optional value, device index to use for the device
- &lt;pcregrep arguments&gt; : optional value, arguments for pcregrep see `man pcregrep` from more information

## examples

```
ioslog
```

> view log

```
ioslog "MyProject"
```

> view lines that contain MyProject

```
ioslog -o1 "{{START}}(.*){{END}}"
```

> view only values between {{START}} to {{END}} on lines that contain {{START}} and {{END}} respectively

## dependencies

### `cfgutil`

- [Installation instructions](https://support.apple.com/en-ca/guide/apple-configurator-2/cad856a8ea58/mac)
- `man cfgutil`

### `pcregrep`

- Install: `brew install pcre`
- `man pcregrep`
