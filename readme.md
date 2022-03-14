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

## Create service
1. Download source code

```git config --global http.sslverify false```

```git clone...```

2. Build project

```cd {project_url}```

```go build cmd/main.go```

3. Create service file

```nano /etc/systemd/system/{service_name}.service```

- pates following code and edit to the service scene

    ```
        [Unit]
        Description=My Webapp Java REST Service
        [Service]
        User=root
        # The configuration file application.properties should be here:

        #change this to your workspace
        WorkingDirectory=/home/skillspar/{service_folder}

        #path to executable. 
        #executable is a bash script which calls jar file
        ExecStart={Path_to_file_build}

        SuccessExitStatus=143
        TimeoutStopSec=10
        Restart=on-failure
        RestartSec=5

        [Install]
        WantedBy=multi-user.target
    ```
   ```
      sudo systemctl daemon-reload
      sudo systemctl enable {service_name}.service
      sudo systemctl start {service_name}
      sudo systemctl status {service_name}
   ```
