FROM jenkins/jenkins:lts

USER root

# Show distro information!
RUN uname -a && cat /etc/*release

# Based on instructiions at https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-current
# Install dependency for .NET Core 2
RUN apt-get update
RUN apt-get install -y curl libunwind8 gettext apt-transport-https

# Based on instructions at https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-current
# Install microsoft.qpg & Install the .NET Core framework 
RUN wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg 
RUN     mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/ 
RUN     wget -q https://packages.microsoft.com/config/debian/9/prod.list 
RUN     mv prod.list /etc/apt/sources.list.d/microsoft-prod.list 
RUN    chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg 
RUN     chown root:root /etc/apt/sources.list.d/microsoft-prod.list
RUN     apt-get update
RUN     apt-get install -y dotnet-sdk-2.1

# Install Docker Support
RUN apt-get update
RUN apt-get -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"

RUN apt-get update
RUN apt-get -y install docker-ce

# Switch back to the jenkins user.
USER jenkins