.PHONY: linux-dependencies python-dependencies build get-chrome build-chrome compress-and-download-chrome teardown

linux-dependencies:
	sudo packman -S python3-pip zip
	echo "aws-sam-cli-bin is also required in order to test the package"

python-dependencies:
	pip install ansible boto boto3 aws-sam-cli

build:
	echo "Building both architectures takes roughly 5 hours"
	ansible-playbook plays/chromium.yml -i inventory.ini

only-get-chrome:
	ansible-playbook plays/chromium.yml -i inventory.ini --tags get-chrome

only-build-chrome:
	ansible-playbook plays/chromium.yml -i inventory.ini --tags build-chrome

only-compress-and-download-chrome:
	ansible-playbook plays/chromium.yml -i inventory.ini --tags compress-and-download-chrome

only-teardown:
	ansible-playbook plays/chromium.yml -i inventory.ini --tags teardown
