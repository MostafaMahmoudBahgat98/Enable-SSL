# Enable-SSL-Certificate
Enable SSL/Certificate on superset
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
prerequisite:
1-Docker 
2-SuperSet
3-Git
4-SSL/Certificate Files
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-install Docker on CentOS9

1-Install the required dependencies:
                                                            $ sudo dnf install -y yum-utils
2-Add the Docker repository:
                                                            $ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
3-Install Docker Engine:
                                                            $ sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
4-Start and enable Docker:
                                                            $ sudo systemctl start docker
                                                            $ sudo systemctl enable docker
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-Install SuperSet Using Docker Compose
****Requirements****
1-Clone Superset's GitHub repository
                                                            $ git clone --depth=1  https://github.com/apache/superset.git
                                                            
2-Launch Superset Through Docker Compose (I use docker-compose-image-tag.yml) 
                                                            $ docker compose -f docker-compose-image-tag.yml up
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-Config SSL Certificte:
I have two files (anyname.crt and anyname.key)
They should be on these paths 
1-/etc/ssl/certs/anyname.crt
2-/etc/ssl/private/anyname.key
-Two files will be modified before command docker compose: (nginx.conf and docker-compose-image-tag.yml)
1-superset/docker/nginx/nginx.conf
2-superset/docker-compose-image-tag.yml
