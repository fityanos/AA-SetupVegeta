# vegeta
How to set up vegeta load testing lib

1. Visit [GitHub](https://github.com/tsenart/vegeta)

2. brew update

3. brew install vegeta

4. brew install go --cross-compile-common

5. vi .zshrc || subl .zshrc || nano ~./zshrc
    
```
include:
   export GOPATH=$HOME/Workspace/go
   export PATH=$PATH:$GOPATH/bin
```

6. Save changes and run `source ~/.zshrc`

7. run this command `go get -u github.com/tsenart/vegeta`

8. PULL MASTER



#### Reference Links:

[https://github.com/tsenart/vegeta](https://github.com/tsenart/vegeta)

[https://testdetective.com/performance-testing-vegeta-attack/](https://testdetective.com/performance-testing-vegeta-attack/)

[https://thisdata.com/blog/load-testing-api-interfaces-with-go-and-vegeta/](https://thisdata.com/blog/load-testing-api-interfaces-with-go-and-vegeta/)


####How to run from command line:

1- In case of GET endpoint without required body:

```bash
vegeta attack -targets=targets.txt -rate=10 -duration=10s | vegeta report
```

2- In case of POST endpoint and i need body:

`Create body.json file and include it in targets.txt AND make sure that lines order matters`

`FIRST the endpoint THEN the headers THEN the body.json path (complete path) WITHOUT SPACES IN BETWEEN`

```bash
vegeta attack -targets=targets.txt -rate=10 -duration=30s | vegeta report
```

3- To save report result in text file you can run the command as follow:

```bash
vegeta attack -targets=targets.txt -rate=10 -duration=5s | vegeta report > anas.bin
```

4- To generate different report you can run the command as follow:

```bash
vegeta attack -targets=targets.txt -rate=10 -duration=5s | vegeta report -reporter=json
```

5- To just dump vegeta report as a raw data

```bash
vegeta attack -targets=targets.txt -rate=10 -duration=5s | vegeta dump
```

6- To use vegeta with jplot and jagger

```bash
vegeta attack -targets=targets.txt -rate=20 -duration=15m | vegeta dump | \
     jaggr @count=rps \
           hist\[200,300,301,400,404,500,502,503\]:code \
           p30,p50,p85:latency \
           sum:bytes_in \
           sum:bytes_out | \
     jplot rps+code.hist.200+code.hist.300+code.hist.301+code.hist.400+code.hist.404+code.hist.500+code.hist.502+code.hist.503 \
           latency.p85+latency.p50+latency.p30 \
           bytes_in.sum+bytes_out.sum
```