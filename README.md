# ProjetoMedusa
Documentação referente ao projeto - Brute Force com Medusa.



 

PROJETO: ATAQUES DE FORÇA BRUTA COM MEDUSA EM AMBIENTE CONTROLADO 

 

SOBRE O PROJETO 

Este repositório faz parte da atividade prática do curso de Cibersegurança. 

O objetivo foi configurar um ambiente controlado com Kali Linux, Metasploitable 2 e realizar diferentes tipos de ataques de força bruta utilizando a ferramenta Medusa, documentando todo o processo. 

O foco é entender como essas técnicas funcionam, como são exploradas por atacantes e quais medidas de mitigação podem ser aplicadas posteriormente. 

 

TOPOLOGIA DO AMBIENTE 

O laboratório foi configurado no VirtualBox, utilizando rede Host-only, permitindo comunicação apenas entre as VMs. 

 

PREPARAÇÃO DO AMBIENTE 

Máquinas utilizadas: 

Kali Linux (atacante) 

Metasploitable 2 (alvo vulnerável com FTP e SMB) 

 

Configurações importantes: 

Ambas as máquinas colocadas em rede Host-only 

Teste de conectividade: 

ping 192.168.56.102 

 

 

ATAQUES REALIZADOS 

A seguir, estão documentados os ataques de força bruta feitos com o Medusa. Cada teste foi executado com uma lista simples para fins educacionais. 

 

1. ATAQUE DE FORÇA BRUTA EM FTP (METASPLOITABLE 2) 

Criação das Wordlists (User e Pass) 

 

Tentativa de login via FTP utilizando as wordlsits 

 

Comando utilizado: 

medusa -h 192.168.56.102 -u user.txt -P pass.txt -M ftp 

 

Objetivo: 

Encontrar a senha do usuário msfadmin via ataque de força bruta no serviço FTP. 

Resultado: 

Credenciais encontradas com sucesso. 

 

2. ATAQUE EM FORMULÁRIO WEB – DVWA (BRUTE FORCE) 

Tentativa de acessar o site com as credenciais encontradas 

Tentativa sem sucesso, mas captura dos campos do formulário 

 

Nova tentativa utilizando Medusa 

Objetivo: 

Realizar brute force no login web do DVWA. 

 

Resultado: 

Senha correta encontrada. 

 

Login realizado com sucesso no painel administrativo. 

 

 

3. PASSWORD SPRAYING EM SMB 

Encontrando usuários com enum4linux 

 

Utilização de relatório TXT e análise com less 

 

Tentativa de Password Spraying nos usuários identificados 

Objetivo: 

Identificar usuários que utilizam senha fraca ou padrão. 

Resultado: 

Usuários vulneráveis identificados. 

 

 

 

 

VALIDAÇÃO DOS ACESSOS 

Após encontrar credenciais válidas, foi feita a validação dos logins via smbclient. 

 

 

MEDIDAS DE MITIGAÇÃO 

Implementar política de senhas fortes 

Configurar bloqueio após múltiplas tentativas de login 

Habilitar MFA sempre que possível 

Restringir serviços FTP e SMB 

Monitorar logs e habilitar auditoria 

Utilizar Firewall, IDS ou IPS 

Manter sistemas e serviços atualizados 

 

CONCLUSÃO 

Este projeto permitiu compreender na prática como ataques de força bruta são realizados e como ferramentas como o Medusa podem ser usadas em auditorias de segurança.  

A atividade reforçou a importância de controles preventivos, monitoramento e políticas adequadas de segurança. 

 
