## Instalação do Moby (Docker Engine) e Docker Compose.

Reativando o cgroups v1 no Fedora.
```bash
> sudo grubby --update-kernel=ALL --args="systemd.unified_cgroup_hierarchy=0"
```

Garantindo que o Docker tenha acesso de redes necessários para gerenciar os containers.
```bash
> sudo firewall-cmd --permanent --zone=trusted --add-interface=docker0
> sudo firewall-cmd --permanent --zone=FedoraWorkstation --add-masquerade
```

Instalação do [`moby-engine`](https://mobyproject.org/).
```bash
> sudo dnf install moby-engine -y
> sudo dnf enable --now docker.service
> sudo usermod --append --groups docker ewerton
```

Para finalizar, `reboot`.

Instalação do [`Docker Compose`](https://docs.docker.com/compose/install/).
```bash
> sudo curl -L "https://github.com/docker/compose/releases/download/1.28.6/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
> sudo chmod +x /usr/local/bin/docker-compose
```