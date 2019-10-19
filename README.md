# bash-ioslog

bash script to use cfgutil syslog and get log information

## Install

```
curl -o <path>/ioslog https://raw.githubusercontent.com/popmedic/bash-ioslog/master/ioslog && \
chmod guo+x <path>/ioslog
```

## Usage

`ioslog <pcregrep arguments>`

### examples

only show lines that have the word MyProject in them

```
ioslog MyProject
```

show the contents between {{START}} and {{END}} on a line

```
ioslog -o1 "{{START}}(.*){{END}}"
```

## Dependencies

### cfgutils 

[Installation instructions](https://support.apple.com/en-ca/guide/apple-configurator-2/cad856a8ea58/mac)

Manual

```
man cfgutil
```


### pcregrep

To install

```
brew install pcre
```

Manual

```
man pcregrep
```
