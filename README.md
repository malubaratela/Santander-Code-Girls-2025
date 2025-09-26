# Desafio - Gerenciando Instâncias EC2 na AWS

Este repositório apresenta um fluxo básico de utilização dos serviços Amazon EC2, EBS e S3 na AWS.

<img width="582" height="254" alt="Diagrama - Fluxo EC2 + EBS + Snapshot-Page-1 drawio" src="https://github.com/user-attachments/assets/e0076c39-473b-4d3e-9619-6d1e6106f0c9" />

## Fluxo EC2 + EBS + S3

### User (Usuário)  
É quem acessa a aplicação. Pode ser uma pessoa entrando no site ou sistema hospedado na nuvem.  

### EC2 (Elastic Compute Cloud)  
O Amazon EC2 é o serviço de computação em nuvem da AWS.  
Ele permite criar máquinas virtuais sob demanda, escolhendo sistema operacional, CPU, memória e rede.  
Na prática, a EC2 é usada para hospedar aplicações, rodar servidores web, processar dados e executar tarefas que exigem escalabilidade.  

### EBS (Elastic Block Store)  
O Amazon EBS é um serviço de armazenamento em blocos que funciona como um “disco rígido” para as instâncias EC2.  
Ele é ideal para guardar dados que precisam ser persistentes, como:  
- Arquivos de configuração,  
- Logs de aplicação,  
- Bancos de dados,  
- Sistemas de arquivos.  

Diferente do armazenamento temporário que algumas instâncias EC2 oferecem, o EBS mantém os dados mesmo que a instância seja desligada ou reiniciada.  

### Amazon S3 (Simple Storage Service)  
O Amazon S3 é o serviço de armazenamento de objetos da AWS.  
Ele é altamente escalável e durável, sendo usado para guardar desde arquivos simples (como imagens e documentos) até grandes volumes de dados.  
No caso do EBS, o S3 armazena **snapshots**, que são cópias de segurança incrementais do volume.  
Esses snapshots permitem restaurar dados em caso de falhas, criar backups automáticos e até replicar ambientes em diferentes regiões.  

### Novo EBS a partir de Snapshot  
A partir dos snapshots armazenados no S3, é possível criar novos volumes EBS.  
Esse recurso é útil em situações como:  
- Recuperação de desastres,  
- Migração de sistemas para outra região ou conta,  
- Criação de ambientes de teste ou homologação com os mesmos dados da produção.  

Esses novos volumes podem ser conectados a outras instâncias EC2, garantindo a continuidade do funcionamento da aplicação e a flexibilidade de uso.  
