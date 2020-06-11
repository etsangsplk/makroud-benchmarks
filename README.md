# Makroud benchmark

> **NOTE:** A benchmark is always an observation, not a measurement of performance.

## Requirements

At least **Go 1.14.0**.

## Setup

First of all, install latest version of others library:

```bash
go get -u -v "github.com/go-gorp/gorp"
go get -u -v "github.com/go-xorm/xorm"
go get -u -v "github.com/jinzhu/gorm"
go get -u -v "github.com/jmoiron/sqlx"
```

> **NOTE:** This benchmark doesn't include **[SQLBoiler](https://github.com/volatiletech/sqlboiler)**
> and **[Kallax](https://github.com/src-d/go-kallax)** since they rely on code generation and not reflection.

## Execute

```bash
go test -run=XXX -bench=SelectAll -benchmem -benchtime=10s
go test -run=XXX -bench=SelectSubset -benchmem -benchtime=10s
go test -run=XXX -bench=SelectComplex -benchmem -benchtime=10s
go test -run=XXX -bench=Insert -benchmem -benchtime=10s
go test -run=XXX -bench=Update -benchmem -benchtime=10s
go test -run=XXX -bench=Delete -benchmem -benchtime=10s
```

## Benchmark graph

```bash
cd graph && python3 graph.py
```

![SelectAll NsOp](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_all_nsop.png)
![SelectAll Bop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_all_bop.png)
![SelectAll Aop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_all_aop.png)
![SelectSubset NsOp](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_subset_nsop.png)
![SelectSubset Bop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_subset_bop.png)
![SelectSubset Aop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_subset_aop.png)
![SelectComplex NsOp](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_complex_nsop.png)
![SelectComplex Bop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_complex_bop.png)
![SelectComplex Aop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/select_complex_aop.png)
![Insert NsOp](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/insert_nsop.png)
![Insert Bop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/insert_bop.png)
![Insert Aop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/insert_aop.png)
![Update NsOp](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/update_nsop.png)
![Update Bop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/update_bop.png)
![Update Aop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/update_aop.png)
![Delete NsOp](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/delete_nsop.png)
![Delete Bop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/delete_bop.png)
![Delete Aop](https://raw.githubusercontent.com/ulule/makroud-benchmarks/master/graph/images/delete_aop.png)

## Acknowledgement

**SQLX** queries in this benchmark could be optimized.

However, since **Makroud** is built on top of **SQLX**, this benchmark highlight the difference of
performance using the same instructions.

**In every case**, using **SQLX** with a optimized workflow is more efficient than **Makroud**.

## Test Machine

```
OS:     Archlinux x86_64 Linux-4.18.8
CPU:    Intel(R) Core(TM) i7-7500U CPU @ 2.70GHz
Memory: 16GB
Go:     go version go1.11.2 linux/amd64
```

## Credits

- [SQLBoiler Benchmark repository](https://github.com/volatiletech/boilbench)
