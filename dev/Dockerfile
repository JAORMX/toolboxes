FROM registry.fedoraproject.org/fedora-toolbox:41

RUN dnf install -y \
	dnf-plugins-core

RUN sudo dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo
RUN sudo dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo

RUN dnf install -y \
	fish \
	neovim \
	golang \
	go-task \
	jq \
	podman \
	docker \
	docker-compose-plugin \
	poetry

RUN sudo dnf install -y gh --repo gh-cli
