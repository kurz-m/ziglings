# Use the latest Ubuntu image as base
FROM ubuntu:latest

# Install required packages
RUN apt-get update && \
    apt-get install -y curl git build-essential valgrind && \
    rm -rf /var/lib/apt/lists/*

# Run the installation script for zvm
RUN curl https://raw.githubusercontent.com/tristanisham/zvm/master/install.sh | bash

# Set up the environment variables
RUN echo "# ZVM" >> $HOME/.profile && \
    echo "export ZVM_INSTALL=\"$HOME/.zvm/self\"" >> $HOME/.profile && \
    echo "export PATH=\"$PATH:$HOME/.zvm/bin\"" >> $HOME/.profile && \
    echo "export PATH=\"$PATH:$ZVM_INSTALL/\"" >> $HOME/.profile

# Define the command to run on container start
CMD ["/bin/bash"]
