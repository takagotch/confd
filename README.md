### confd
---
https://github.com/kelseyhightower/confd

```
mkdir -p $GOPATH/src/github.com/kelseyhightower
git clone https://github.com/kelseyhightower/confd.git $GOPATH/src/github.com/kelseyhightower/confd
cd $GOPATH/src/github.com/kelseyhightower/confd
make

ls bin/
```

```
upstream {{getv "/subdomain"}} {
{{range getvs "/upstream/*"}}
  server {{.}};
{{end}}
}

server {
  server_name {{getv "/subdomain"}}.example.com;
  location / {
    proxy_pass http://{{getv "/subdomain"}};
    proxy_redirect off;
    proxy_set_header Host $host;
    proxy_set_header X-Real-Ip $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  }
}

```

```
```


