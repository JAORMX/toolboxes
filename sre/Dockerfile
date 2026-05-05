FROM registry.fedoraproject.org/fedora-toolbox:44

RUN dnf install -y \
	dnf-plugins-core \
	fish \
	neovim \
	jq \
	podman \
	opentofu \
	awscli2 \
	kubernetes-client \
	fzf && \
    dnf clean all
