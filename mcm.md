Build local release
===================

```
git clone git@github.com:mc-media/croc.git
cd croc
VERSION=$(git tag | tail -n1  | sed 's/^v//')mcm go run src/install/updateversion.go
go build -v -ldflags="-s -w"
```
