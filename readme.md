## How to deploy golang project to server

1. Install Go environment

![image](https://user-images.githubusercontent.com/51145983/158132443-70782b6e-d348-48a8-b076-43c6d90a9c80.png)

- Download tar file

```cd ~```

```curl -OL https://golang.org/dl/go1.16.7.linux-amd64.tar.gz```

- Verify the integrity of the file downloaded

```sha256sum go1.16.7.linux-amd64.tar.gz```

- Install

```sudo tar -C /usr/local -xvf go1.16.7.linux-amd64.tar.gz```

2. Setting Go Paths

```sudo nano ~/.profile```

![image](https://user-images.githubusercontent.com/51145983/158134201-1421e737-bdef-470a-b59d-07964e2e8158.png)

```source ~/.profile```

```go version```
