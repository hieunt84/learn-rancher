## Setup Rancher
v.2.4.5

## Ref
- https://xuanthulab.net/su-dung-rancher-de-quan-ly-kubernetes-cluster.html
- https://rancher.com/quick-start/

## ENVIRONMENT
- Developing on vagrant
- Testing on vagrant


### setup rancher v2.4.8 on vm using docker
    docker run -d --restart=unless-stopped \
        -p 80:80 -p 443:443 \
        -v /opt/rancher:/var/lib/rancher \
        rancher/rancher:v2.4.8
    
    Note: khi rancher kết nối k8s thì 2 thành phần control-plane and scheduler bị unhealthy
    - điều này là bình thường
    - do rancher v2.4.8 dùng cách kết nối unsecure để lấy thông tin từ k8s, mà k8s đang có kế hoạch     không dùng kết nối này nữa.    
    
    Account quản trị Rancher: admin/Password@2021     

### setup rancher version lastest v2.5.8 on vm using docker
    docker run -d --restart=unless-stopped --privileged \
        -p 80:80 -p 443:443 \
        -v /opt/rancher:/var/lib/rancher \
        rancher/rancher