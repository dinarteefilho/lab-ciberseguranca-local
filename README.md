# Laboratório de Cibersegurança Local (DevSecOps)

Um ambiente de laboratório isolado e conteinerizado, focado na simulação de ataques a aplicações web e no monitoramento contínuo da infraestrutura. 

## Objetivo do Projeto
Este projeto tem como finalidade demonstrar na prática a exploração de vulnerabilidades e a aplicação de defesas (Red Team & Blue Team). A infraestrutura foi montada integralmente via código, garantindo um ambiente seguro, reprodutível e monitorado.

## Arquitetura e Tecnologias
A aplicação vulnerável e o sistema de monitoramento rodam de forma isolada em uma rede virtual.
*   **Orquestração:** Docker & Docker Compose
*   **Aplicação Alvo:** DVWA (Damn Vulnerable Web Application)
*   **Monitoramento:** Zabbix Server & Nginx
*   **Banco de Dados:** MySQL

## Cenários de Teste Documentados
Neste laboratório, as seguintes simulações foram executadas e documentadas (veja a pasta `/docs`):

1.  **Descoberta e Mapeamento:** Utilização de ferramentas como FFUF para enumeração de diretórios e arquivos ocultos na aplicação alvo.
2.  **Exploração de Falhas:** Execução prática de Command Injection para estabelecimento de um *Reverse Shell* dentro do container.
3.  **Teste de Estresse (DoS):** Simulação de ataque *Slowloris* visando o esgotamento de recursos do servidor web.
4.  **Monitoramento Ativo:** Captura e análise do comportamento da CPU e do tráfego de rede durante os ataques através dos dashboards do Zabbix.

## Como Executar Localmente
Para subir o laboratório na sua máquina, certifique-se de ter o Docker instalado e rode o seguinte comando na raiz do projeto:

\`\`\`bash
docker-compose up -d
\`\`\`
*   A aplicação DVWA estará disponível em: `http://localhost:8080`
*   O painel do Zabbix estará disponível em: `http://localhost:8081`