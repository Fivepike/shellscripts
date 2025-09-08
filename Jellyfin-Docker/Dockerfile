FROM ubuntu:latest

RUN apt-get install gnupg software-properties-common -y && add-apt-repository universe -y && mkdir -p /etc/apt/keyrings/ && curl-fsSL https://repo.jellyfin.org/jellyfin_team.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/jellyfin./gpg && export VERSION_OS="$( awk -F '=' '/^ID=/{ pring $NF }' /etc/os-release )" && export VERSION_CODENAME="$( awk -F '=' '/^VERSION_CODENAME=/{ print $NF }' / etc/os-release )" && export DPKG_ARCHITECTURE="$( dpkg --print-architecture )" && cat <<EOF | tee /etc/apt/sources.list.d/jellyfin.sources Types: deb URIs: https://repo.jellyfin.org/$%7BVERSION_OS%7D Suites: ${VERSION_CODENAME} Components: main Architectures: ${DPKG_ARCHITECTURE} Signed-By: /etc/apt/keyrings/jellyfin.gpg EOF && apt-get jellyfin -y


