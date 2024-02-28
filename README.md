[![Go Reference](https://pkg.go.dev/badge/github.com/gontainer/graph.svg)](https://pkg.go.dev/github.com/gontainer/graph)
[![Tests](https://github.com/gontainer/graph/actions/workflows/tests.yml/badge.svg)](https://github.com/gontainer/graph/actions/workflows/tests.yml)
[![Coverage Status](https://coveralls.io/repos/github/gontainer/graph/badge.svg?branch=main)](https://coveralls.io/github/gontainer/graph?branch=main)
[![Go Report Card](https://goreportcard.com/badge/github.com/gontainer/graph)](https://goreportcard.com/report/github.com/gontainer/graph)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=gontainer_graph&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=gontainer_graph)

# Graph

This package provides a tool to detect circular dependencies and find all dependant nodes in directed graphs.

```go
g := graph.New()
g.AddDep("company", "tech-team")
g.AddDep("tech-team", "cto")
g.AddDep("cto", "company")
g.AddDep("cto", "ceo")
g.AddDep("ceo", "company")

fmt.Println(g.CircularDeps())

// Output:
// [[company tech-team cto company] [company tech-team cto ceo company]]
```

See [examples](examples_test.go).
