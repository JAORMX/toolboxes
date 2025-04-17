FROM registry.fedoraproject.org/fedora-toolbox:42

RUN dnf install -y \
	dnf-plugins-core

RUN dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo
RUN dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo

# Install Node.js repository
RUN dnf install -y nodejs npm

# Install common development tools and Node.js specific tools
RUN dnf install -y \
	fish \
	neovim \
	jq \
	podman \
	docker \
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
