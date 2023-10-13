[![Go Analyzer](https://goanalyzer.khulnasoft.com/badge/khulnasoft-lab/goanalyzer)](https://goanalyzer.khulnasoft.com/report/khulnasoft-lab/goanalyzer) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/khulnasoft-lab/goanalyzer/blob/master/LICENSE)

# Go Analyzer

A web application that generates a report on the quality of an open source Go project. It uses several measures, including `gofmt`, `go vet`, `go lint` and `gocyclo`. To get a report on your own project, try [goanalyzer.khulnasoft.com](https://goanalyzer.khulnasoft.com).

### Sponsors

Support us over on [Patreon](https://www.patreon.com/goanalyzer)!

### Installation

```
git clone https://github.com/khulnasoft-lab/goanalyzer.git
cd goanalyzer
make install
```

Now run:

```
GRC_DATABASE_PATH=./db make start
```

and you should see

```
Running on :8000...
```

Navigate to `localhost:8000` and you should see the Go Analyzer front page.

### Command Line Interface

There is also a CLI available for grading applications on your local machine.

Example usage:
```
git clone https://github.com/khulnasoft-lab/goanalyzer.git
cd goanalyzer
make install
go install ./cmd/goanalyzer-cli
goanalyzer-cli
```

```
Grade .......... A+  99.9%
Files ................ 362
Issues ................. 2
gofmt ............... 100%
go_vet ............... 99%
gocyclo .............. 99%
golint .............. 100%
ineffassign ......... 100%
license ............. 100%
misspell ............ 100%
```

Verbose output:

```
goanalyzer-cli -v
```

```
Grade .......... A+  99.9%
Files ................ 362
Issues ................. 2
gofmt ............... 100%
go_vet ............... 99%
go_vet  vendor/github.com/prometheus/client_golang/prometheus/desc.go:25
        error: cannot find package "github.com/prometheus/client_model/go" in any of: (vet)

gocyclo .............. 99%
gocyclo download/download.go:22
        warning: cyclomatic complexity 17 of function download() is high (> 15) (gocyclo)

golint .............. 100%
ineffassign ......... 100%
license ............. 100%
misspell ............ 100%
```

### Contributing

Go Analyzer is an open source project run by volunteers, and contributions are welcome! Check out the [Issues](https://github.com/khulnasoft-lab/goanalyzer/issues) page to see if your idea has already been mentioned. Feel free to raise an issue or submit a pull request.

### Academic Citation

If you use Go Analyzer for academic purposes, please use the following citation:

```
@Misc{schaaf-smith-goanalyzer,
    author = {Schaaf, Herman and Smith, Shawn},
    title  = {Go Analyzer: A report card for your Go application},
    year   = {2015--},
    url    = {https://www.goanalyzer.khulnasoft.com/},
    note   = {[Online; accessed <today>]}
}
```

### License

The code is licensed under the permissive Apache v2.0 license. [Read this](https://tldrlegal.com/license/apache-license-2.0-(apache-2.0)) for a summary.
