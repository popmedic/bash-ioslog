# ioslog

bash script to use cfgutil syslog and get log information

## usage

```
<idx=[device index]> ioslog <pcregrep arguments>
```

where:
- &lt;idx=[device index]&gt; : optional value, device index to use for the device
- &lt;pcregrep arguments&gt; : optional value, arguments for pcregrep see `man pcregrep` from more information

## examples

> view log

```
ioslog
```

> view lines that contain MyProject

```
ioslog "MyProject"
```

> view only values between {{START}} to {{END}} on lines that contain {{START}} and {{END}} respectively

```
ioslog -o1 "{{START}}(.*){{END}}"
```

## dependencies

### `cfgutils`

- [Installation instructions](https://support.apple.com/en-ca/guide/apple-configurator-2/cad856a8ea58/mac)
- `man cfgutils`

### `pcregrep - brew install pcre`

- Install: `brew install pcre`
- `man pcregrep`
