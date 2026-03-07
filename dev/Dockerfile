FROM registry.fedoraproject.org/fedora-toolbox:43

RUN dnf install -y dnf-plugins-core && \
    dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo && \
    echo "exclude=docker*" >> /etc/yum.repos.d/fedora.repo && \
    echo "exclude=docker*" >> /etc/yum.repos.d/fedora-updates.repo && \
    dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo && \
    dnf -y distro-sync --refresh && \
    dnf install -y --skip-unavailable \
	fish \
	neovim \
	golang \
	go-task \
	jq \
	podman \
	docker-ce \
	docker-ce-cli \
	docker-buildx-plugin \
	docker-compose-plugin \
	poetry && \
    dnf install -y gh --repo gh-cli && \
    dnf clean all
