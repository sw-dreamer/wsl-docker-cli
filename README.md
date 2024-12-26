### Docker CLI (옵션)

Docker CLI만 설치하고 Docker Desktop을 사용하지 않으려면, Docker의 CLI 도구를 WSL 배포판에 설치할 수 있습니다. 예를 들어, Ubuntu에서 Docker를 설치하려면 아래 명령어를 실행하세요:

```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
```
그 후, docker 명령어가 제대로 작동하는지 확인합니다
```bash
docker --version
```
Docker 권한 설정 (옵션)
WSL 환경에서 Docker 명령어를 sudo 없이 사용하려면, Docker 그룹에 사용자 계정을 추가해야 합니다
```
sudo usermod -aG docker $USER
```
