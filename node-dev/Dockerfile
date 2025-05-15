FROM registry.fedoraproject.org/fedora-toolbox:42

RUN dnf install -y \
	dnf-plugins-core

# Add Docker CE repository and exclude conflicting packages from Fedora repos
RUN dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo && \
    echo "exclude=docker*" >> /etc/yum.repos.d/fedora.repo && \
    echo "exclude=docker*" >> /etc/yum.repos.d/fedora-updates.repo

RUN dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo

# Run distro-sync to ensure we have the latest package info
RUN dnf -y distro-sync --refresh

# Install Node.js repository
RUN dnf install -y nodejs npm

# Install common development tools and Node.js specific tools
RUN dnf install -y  --skip-unavailable \
	fish \
	neovim \
	jq \
	podman \
	docker-ce \
	docker-ce-cli \
	docker-buildx-plugin \
	docker-compose-plugin \
	git \
	make \
	gcc-c++ \
	python

RUN dnf install -y gh --repo gh-cli

# Install global NPM packages
RUN npm install -g \
	yarn \
	pnpm \
	typescript \
	ts-node \
	nodemon \
	@angular/cli \
	create-react-app \
	create-next-app \
	eslint \
	prettier
