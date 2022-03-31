### Docker 완전 삭제
1. docker container 중지, 삭제
2. local에 저장된 image 삭제
3. docker service, container service 중지
4. docker package 삭제
5. /var/lib/docker 아래 모든 파일, 디렉토리 삭제
6. /var/run 아래 docker.sock, docker.pid, docker 디렉토리 삭제
```
[root@cent1 ~]# systemctl stop docker
[root@cent1 ~]# systemctl stop containerd
[root@cent1 ~]# yum list installed | grep docker

# 패키지 삭제
root@cent1 ~]# yum remove -y containerd.io.x86_64
[root@cent1 ~]# yum remove -y docker-ce.x86_64
[root@cent1 ~]# yum remove -y docker-ce-cli.x86_64

# 리스트 확인
[root@cent1 ~]# yum list installed | grep docker

# 관련 파일, 디렉토리 수동 삭제
[root@cent1 ~]# cd /var/lib/docker
[root@cent1 docker]# rm -rf *
[root@cent1 docker]# cd /var/run
[root@cent1 run]# rm -f docker.sock docker.pid
[root@cent1 run]# rm -rf docker
```
