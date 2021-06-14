# Launching JNLP Files
JNLP is a commonly used file type in KVMs and iDRAC. There are many other uses as well as it's
a very robust protocol. After Java 11, it seems that Java no longer ships with the Java Web 
Start binary. These are the steps I've used to run these files today.

## Install IcedTea-Web
Download and install [IcedTea-Web](https://www.azul.com/products/components/icedtea-web/)

## Run JNLP using IcedTea-Web
Run the JNLP using the following command

```batch
"C:\Path\to\IcedTea-Web\javaws.exe" -nosecurity "C:\Path\to\file.jnlp"
```

**Warning**: Use the `-nosecurity` flag at your own risk!
