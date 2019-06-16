#!make
SHELL := /bin/bash

.PHONY: apps
apps:
	cd apps/ && docker-compose up -d

.PHONY: mgmt
mgmt: decrypt
	cd mgmt/ && docker-compose up -d

.PHONY: encrypt
encrypt: secrets.enc
secrets.enc:
	openssl enc -aes-256-cbc -in secrets -out secrets.enc

.PHONY: decrypt
decrypt: secrets
secrets:
	openssl enc -d -aes-256-cbc -in secrets.enc -out secrets
