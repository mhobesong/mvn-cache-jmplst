# mvn-cache-jmplst
Script for generation .jmplst file from jdk and mvn cache to use in Vim JavaImp plugin.

I have been using VIM for a while now for all my development. Recently, I was building som Java apps 
and had some issues with auto-completting Java import statements. After a few Googling, I feel on [JavaImp](https://www.vim.org/scripts/script.php?script_id=325). 

I crafted the following bash command to help generate an import cache for Java Standard Lib.

```bash
jar tf /usr/lib/jvm/java-1.8.0-openjdk-amd64/jre/lib/rt.jar | sed  -e 's#^src/##' > jdk.jmplst
```

For my maven download cache I use

```bash
find ~/.m2/repository/ -name *.jar -type f -exec jar -tf {} \; | sed  -e 's#^src/##' > jdk.jmplst
```
