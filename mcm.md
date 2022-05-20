Build local release
===================

```
git clone git@github.com:mc-media/croc.git
cd croc
VERSION=$(git tag | tail -n1  | sed 's/^v//')mcm go run src/install/updateversion.go
go build -v -ldflags="-s -w" -o croc_linux
GOOS=windows GOARCH=amd64 go build -v -ldflags="-s -w" -o croc_windows.exe
GOOS=darwin GOARCH=amd64 go build -v -ldflags="-s -w" -o croc_darwin
```
