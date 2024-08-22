# minio-disk
> copy from github.com/minio/minio commit fb4ad000b6fc25e577b9b76402e91d1dc6f4cc0c

## usage

### install
```sh
go get -u github.com/naughtyGitCat/minio-disk
```

```go
import (
        "github.com/naughtyGitCat/minio-disk"
        humanize "github.com/dustin/go-humanize"
)

func printUsage(path string) error {
        di, err := disk.GetInfo(path)
        if err != nil {
            return err
        }
        percentage := (float64(di.Total-di.Free)/float64(di.Total))*100
        fmt.Printf("%s of %s disk space used (%0.2f%%)\n", 
            humanize.Bytes(di.Total-di.Free), 
            humanize.Bytes(di.Total), 
            percentage,
        )
}
```


## ref
- https://stackoverflow.com/questions/59342373/use-of-internal-package-not-allowed
- https://stackoverflow.com/questions/20108520/get-amount-of-free-disk-space-using-go
