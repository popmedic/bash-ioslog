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

- `<idx=[device index]>` : optional value, device index to use for the device
- `<pcregrep arguments>` : optional value, arguments for pcregrep see `man pcregrep` from more information

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
idx=1 ioslog -oi "[\[0-9a-f\]\{8\}]{.*?}"
```

> using the device at index 1, view value from "[" followed by a hex value 8 characters long then "]{" 
then anything, non greed, ending with a "}"

```
ioslog -o1 "{{START}}(.*){{END}}"
```

> view only values between {{START}} to {{END}} on lines that contain {{START}} and {{END}} 
respectively 

## exit codes

- success: 0
- `cfgutil` not installed: 1011
- no devices attached: 1012
- index of device is out of range for devices: 1013
- unable to parse the device in devices: 1014
- `pcregrep is not installed: 1015

## dependencies

### `cfgutil`

- [Installation instructions](https://support.apple.com/en-ca/guide/apple-configurator-2/cad856a8ea58/mac)
- `man cfgutil`

### `pcregrep`

- Install: `brew install pcre`
- `man pcregrep`
