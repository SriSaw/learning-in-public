# Day 0 — Cloud Native Foundations

## Topics Covered

* Linux Fundamentals
* Networking Basics
* Docker
* Kubernetes
* Git & GitHub
* Go Setup
* VS Code + WSL

---

## Linux

### Navigation

```bash
pwd
ls
ls -a
cd
cd ..
```

### Hidden Files

Examples:

```text
.git
.env
.bashrc
```

### Processes & Signals

```bash
echo $$
sleep 300
```

Common signals:

| Signal  | Meaning       |
| ------- | ------------- |
| SIGINT  | Ctrl+C        |
| SIGTERM | Graceful stop |
| SIGKILL | Force stop    |

---

## Networking

### TCP vs UDP

TCP:

* Reliable
* Ordered

UDP:

* Faster
* No delivery guarantee

### Common Ports

```text
80   HTTP
443  HTTPS
53   DNS
8080 Application Port
```

### Request Flow

```text
Browser
 ↓
DNS
 ↓
TCP
 ↓
HTTP/HTTPS
 ↓
Response
```

### TLS

Provides:

* Encryption
* Authentication
* Integrity

---

## Docker

### Core Concepts

```text
Image     → Blueprint
Container → Running instance
```

### Port Mapping

```bash
docker run -p 8080:80 nginx
```

```text
Host:8080 → Container:80
```

---

## Kubernetes

### Core Objects

#### Pod

Smallest deployable unit.

#### Deployment

Provides:

* Scaling
* Self-healing

#### Service

Stable endpoint for Pods.

```text
Service
 ↓
Pods
```

### Control Plane Components

* kube-apiserver
* etcd
* scheduler
* controller-manager
* CoreDNS
* kube-proxy

### Port Forwarding

```bash
kubectl port-forward service/hello-nginx 8080:80
```

Flow:

```text
Browser
 ↓
localhost:8080
 ↓
Service
 ↓
Pod
 ↓
Container
```

---

## Git & GitHub

### Basic Workflow

```bash
git init
git add .
git commit -m "message"
git log --oneline
```

### Branches

```bash
git checkout -b feature-1
git checkout main
git merge feature-1
```

### SSH Authentication

```bash
ssh-keygen -t ed25519
ssh -T git@github.com
```

---

## Go

Initialize a module:

```bash
go mod init go-arena
```

Run a program:

```bash
go run main.go
```

---

## Build Tooling

### Makefile

```make
run:
	go run main.go
```

```bash
make run
```

### Environment Variables

```bash
export APP_NAME=Battlefield
echo $APP_NAME
```

### .env

```text
APP_NAME=Battlefield
PORT=8080
```

```bash
set -a
source .env
set +a
```

---

## Linux Internals

### Namespaces

Isolation for:

* Processes
* Network
* Mounts

### cgroups

Resource limits:

* CPU
* Memory

### File Descriptors

```text
0 = stdin
1 = stdout
2 = stderr
```

---

## Hands-On Achievements

✅ Created a Kubernetes cluster using kind

✅ Deployed nginx on Kubernetes

✅ Configured GitHub SSH authentication

✅ Created and ran a Go project

✅ Set up VS Code + WSL

---

## Key Takeaways

* Docker containers are isolated Linux processes.
* Kubernetes concepts are easier after understanding Linux and networking.
* Fundamentals matter more than memorizing commands.

Day 0 Complete 🚀
