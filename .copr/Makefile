python_major_version=$(shell command -v python3 &>/dev/null && echo 3 || echo 2)
SRPM_DEPENDENCIES=python$(python_major_version)-setuptools git

srpm:
	rpm -q --whatprovides $(SRPM_DEPENDENCIES) || dnf -y install $(SRPM_DEPENDENCIES)
	$(dir $(realpath $(firstword $(MAKEFILE_LIST))))../packaging/make_srpm.sh
