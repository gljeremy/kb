[[Acoustic]] 



Enables anonymous access to snippets of content for visibility by public search engines as well as an editing interface for managing content

Target users:
Previous employee looking for information
WTW admin user managing content

Repo: EmbarkContent-Libraries
Contains Types, they are very simple

RabbitMQ for local dev
Azure ServiceBus for higher environments

Searchable pages is contained within:
Repo: EmbarkContent-Services -- this repo contains services that are geared towards 10x

VSCode is the primary IDE
Open EmbarkContent-Services in vscode
see README.md first
pipelines folder contain scripts for creating containers that live in k8s locally and on the environments.  In the environments these will live in Bedrock
Needs WSL2 -- it's a good idea to limit WSL to 8gb
run init.ps1

run ./tiltup-compact-sp.ps1 -- this stands up all SearchablePages code.





