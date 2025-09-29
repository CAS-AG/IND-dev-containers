# Python 3.11 base (change to 3.12, etc. if you prefer)
FROM python:3.11-bookworm

# Create a non-root user that matches Dev Containers expectations
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=1000

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

# Useful OS packages for building Python deps
RUN apt-get update && apt-get install -y --no-install-recommends \
        git curl build-essential pkg-config \
    && rm -rf /var/lib/apt/lists/*

# Make sure pip is up-to-date and create a venv (optional but nice)
RUN python -m pip install --upgrade pip \
    && python -m venv /venv

ENV PATH="/venv/bin:${PATH}"

# Set the default workdir (Dev Containers will mount your project here)
WORKDIR /workspaces

# Switch to non-root
USER $USERNAME
