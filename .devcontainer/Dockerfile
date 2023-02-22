FROM mcr.microsoft.com/devcontainers/base:jammy

RUN INSTALL_DIR=/home/vscode/.local/share/solana/install; \
    apt-get update && \
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs > /home/vscode/rust-installer && \
    chmod +x /home/vscode/rust-installer && \
    /home/vscode/rust-installer -y && \
    mv /root/.cargo /home/vscode && \
    chown vscode -R /home/vscode/.cargo && \
    curl -sSfL https://release.solana.com/v1.15.2/install > /home/vscode/solana-installer && \
    chmod +x /home/vscode/solana-installer && \
    /home/vscode/solana-installer --data-dir "$INSTALL_DIR" 1.15.2 && \
    chown vscode -R "$INSTALL_DIR" && \
    echo 'export PATH="'"$INSTALL_DIR"'/active_release/bin:$PATH"; source $HOME/.cargo/env' >> /home/vscode/.bashrc
