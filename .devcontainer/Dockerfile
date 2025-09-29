FROM python:3.12-bookworm

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=1000

# Create user with bash as default shell
RUN groupadd --gid $USER_GID $USERNAME \
 && useradd --uid $USER_UID --gid $USER_GID -m -s /bin/bash $USERNAME

# OS packages
RUN apt-get update && apt-get install -y --no-install-recommends \
        git curl build-essential pkg-config \
    && rm -rf /var/lib/apt/lists/*

# Switch to non-root BEFORE creating the venv so the user owns it
USER $USERNAME 
WORKDIR /workspaces

# Create a per-user venv that vscode owns
RUN python -m pip install --upgrade pip \
    && python -m venv /home/$USERNAME/.venv

ENV PATH="/home/$USERNAME/.venv/bin:${PATH}"


