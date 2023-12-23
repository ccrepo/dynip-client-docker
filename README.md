# Project: Dynip-Client-Docker

Docker build project to clone, build and deploy dynip-client within a runnable docker image.

An internet connection is required as code will be downloaded from github.com during build. 

## Usage

1. Pre-requisites:

    Software:
      
    ```text
    Ubuntu 22.04
    Git client software.
    Docker 24.0.x.
    ```
    
2. Build:

    Building:
    
    Navigate to project home directory.

    cd bin
    
    The following scripts are available.
    
    ```bash
    ./c - this does the full container build and deployment using the project's Dockerfile
    ```

3. Run:

    Log into running container via docker exec -lt ID bash command.

    Navigate to $projectDir/bin

    Run file ./r
