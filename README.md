# vegeta
How to set up vegeta load testing lib

1. Visit [GitHub](https://github.com/tsenart/vegeta)

2. brew update

3. brew install vegeta

4. brew install go --cross-compile-common

5. vi .zshrc
    
```php
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

