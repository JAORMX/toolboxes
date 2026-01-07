FROM registry.fedoraproject.org/fedora-toolbox:43

RUN dnf install -y \
	dnf-plugins-core

# Add Docker CE repository and exclude conflicting packages from Fedora repos
RUN dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo && \
    echo "exclude=docker*" >> /etc/yum.repos.d/fedora.repo && \
    echo "exclude=docker*" >> /etc/yum.repos.d/fedora-updates.repo

RUN dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo

# Run distro-sync to ensure we have the latest package info
RUN dnf -y distro-sync --refresh

RUN dnf install -y --skip-unavailable \
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
	poetry

RUN dnf install -y gh --repo gh-cli
