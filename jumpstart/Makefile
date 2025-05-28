###########################################
#     Run various Ansible playbooks       #
###########################################

.PHONY: help
help: ## Display help message
	@grep -E '^[0-9a-zA-Z_-]+\.*[0-9a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

.PHONY: build
build: ## Create base config from CSV
	ansible-playbook ./playbooks/create_base_configs.yml

.PHONY: dhcpd
dhcpd: ## Create dhcpd config
	ansible-playbook ./playbooks/create_dhcpd_configs.yml

.PHONY: ztp
ztp: ## Create dhcpd config
	ansible-playbook ./playbooks/create_ztp_configs.yml

.PHONY: all
all: ## Create all config
	ansible-playbook ./playbooks/all.yml

.PHONY: avd_inv
avd_inv: ## Create AVD inventory
	ansible-playbook ./playbooks/avd_inventory_builder.yml

.PHONY: all_inv
all_inv: ## Create All devices inventory
	ansible-playbook ./playbooks/all_inventory_builder.yml
