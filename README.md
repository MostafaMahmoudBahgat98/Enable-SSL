# Enable-SSL-Certificate

# Enable SSL/Certificate on Superset
---

## Prerequisites:
1. Docker
2. Superset
3. Git
4. SSL/Certificate Files

---

## Install Docker on CentOS 9

1. Install the required dependencies:
    ```sh
    sudo dnf install -y yum-utils
    ```

2. Add the Docker repository:
    ```sh
    sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    ```

3. Install Docker Engine:
    ```sh
    sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
    ```

4. Start and enable Docker:
    ```sh
    sudo systemctl start docker
    sudo systemctl enable docker
    ```

---

## Install Superset Using Docker Compose

### Requirements

1. Clone Superset's GitHub repository:
    ```sh
    git clone --depth=1 https://github.com/apache/superset.git
    ```

2. Launch Superset through Docker Compose (using `docker-compose-image-tag.yml`):
    ```sh
    docker compose -f docker-compose-image-tag.yml up
    ```

---

## Configure SSL Certificate

You need two files: `anyname.crt` and `anyname.key`.

They should be placed in the following paths:
1. `/etc/ssl/certs/anyname.crt`
2. `/etc/ssl/private/anyname.key`

Two files need to be modified before running the Docker Compose command:
1. `superset/docker/nginx/nginx.conf`
2. `superset/docker-compose-image-tag.yml`
