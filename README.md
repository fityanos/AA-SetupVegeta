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

`vegeta attack -targets=targets.txt -rate=10 -duration=10s | vegeta report`

2- In case of POST endpoint and i need body:

`Create body.json file and include it in targets.txt AND make sure that lines order matters`

`FIRST the endpoint THEN the headers THEN the body.json path (complete path) WITHOUT SPACES IN BETWEEN`

`vegeta attack -targets=targets.txt -rate=10 -duration=30s | vegeta report`

3- To save report result in text file you can run the command as follow:

``

4- To generate different report you can run the command as follow:

`vegeta attack -targets=targets.txt -rate=10 -duration=5s | vegeta report > anas.txt`