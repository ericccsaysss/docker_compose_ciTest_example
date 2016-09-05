# Docker_compose_ciTest_example

**Step 1:** Spin up DigitalOcean droplet: Ubuntu 14.04

**Step 2:** Create user with sudo capabilities

**Step 3:** Install docker 
```bash
  wget -qO- https://get.docker.com/ | sh
```

**Step 4:** Add new user to docker group
```bash
  sudo usermod -aG docker $(whoami)
```

**Step 5:** Install docker-compose
```bash
  sudo apt-get update
  sudo apt-get -y install python-pip
  sudo pip install docker-compose
```

**Step 6:** Clone the repo
```bash
  cd ~/;
  git clone https://github.com/ericccsaysss/docker_compose_ciTest_example.git
```

**Step 7:** Run docker compose and execute tests
```bash
  sudo docker-compose -f ~/docker_compose_ciTest_example/docker-compose.test.yml -p ci up -d
```

**Step 8:** Examine test result(s)
```bash
  docker logs -f ci_sut_1
```
