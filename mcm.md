Build local release
===================

```
git clone git@github.com:mc-media/croc.git
cd croc
export VERSION=$(git tag | tail -n1  | sed 's/^v//')mcm
go run src/install/updateversion.go
export PREFIX=croc_v${VERSION}-$(git rev-parse --short HEAD)
go build -v -ldflags="-s -w" -o ${PREFIX}_linux_amd64
GOOS=windows GOARCH=amd64 go build -v -ldflags="-s -w" -o ${PREFIX}_windows_amd64.exe
GOOS=darwin GOARCH=amd64 go build -v -ldflags="-s -w" -o ${PREFIX}_darwin_amd64
GOOS=darwin GOARCH=arm64 go build -v -ldflags="-s -w" -o ${PREFIX}_darwin_arm64
```
