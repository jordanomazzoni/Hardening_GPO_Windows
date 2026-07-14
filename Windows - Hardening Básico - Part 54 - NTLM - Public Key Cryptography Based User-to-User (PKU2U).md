<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/2074117d-788d-4e8f-b1a2-b42b0d6cae6e" />


# Windows - Hardening Básico - Part 54 - NTLM - Public Key Cryptography Based User-to-User (PKU2U)

Garanta que 'Network security: Allow Local System to use computer identity for NTLM' esteja habilitada como 'Enabled'

Esta configuração de política determina se os serviços do Sistema Local que usam Negociar ao reverter para a autenticação NTLM podem usar a identidade do computador. Esta política tem suporte pelo menos no Windows 7 ou no Windows Server 2008 R2.

O estado recomendado para esta configuração é: Enabled .

Ao se conectar a computadores que executam versões do Windows anteriores ao Windows Vista ou ao Windows Server 2008 (não R2), os serviços executados como Sistema Local e usando SPNEGO (Negociar) que revertem para NTLM usam a identidade do computador. No Windows 7, se você estiver se conectando a um computador que executa o Windows Server 2008 ou o Windows Vista, um serviço do sistema usará a identidade do computador ou uma sessão NULA. Ao conectar-se a uma sessão NULL, é criada uma chave de sessão gerada pelo sistema, que não fornece proteção, mas permite que os aplicativos assinem e criptografem dados sem erros. Ao conectar-se à identidade do computador, tanto a assinatura quanto a criptografia são suportadas para fornecer proteção de dados.



Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Allow Local System to use computer identity for NTLM



Garanta que 'Network security: Restrict NTLM: Audit Incoming NTLM Traffic' esteja habilitada como 'Enable auditing for all accounts'

Esta configuração de política permite a auditoria do tráfego NTLM de entrada. Os eventos para esta configuração são registrados no log de eventos operacionais (por exemplo, Log de Aplicativos e Serviços\Microsoft\Windows\NTLM).

O estado recomendado para esta configuração é: Habilitar auditoria para todas as contas.

A auditoria e o monitoramento do tráfego NTLM podem ajudar na identificação de sistemas que usam esse protocolo de autenticação desatualizado, para que possam ser corrigidos para o uso de um protocolo mais seguro, como o Kerberos. As informações de log coletadas também podem auxiliar em investigações forenses após um ataque malicioso.

A autenticação NTLM e NTLMv2 é vulnerável a vários ataques, incluindo retransmissão SMB, man-in-the-middle e ataques de força bruta. Reduzir e eliminar a autenticação NTLM em um ambiente reduz o risco de um agente de ameaça obter acesso aos sistemas na rede.



Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Restrict NTLM: Audit Incoming NTLM Traffic



Garanta que 'Network security: Restrict NTLM: Outgoing NTLM traffic to remote servers' esteja habilitada como 'Audit all' or higher

Esta configuração de política permite a auditoria do tráfego NTLM de saída. Os eventos para esta configuração são registrados no log de eventos operacionais (por exemplo, Log de Aplicativos e Serviços\Microsoft\Windows\NTLM).

O estado recomendado para esta configuração é: Auditar tudo. Definir essa configuração como Negar tudo também está em conformidade com o benchmark.

Observação: definir essa configuração como Negar tudo é mais seguro, mas pode ter um impacto negativo em aplicativos que ainda exigem NTLM. Teste cuidadosamente antes de implementar o valor Deny All.

A auditoria e o monitoramento do tráfego NTLM podem ajudar na identificação de sistemas que usam esse protocolo de autenticação desatualizado, para que possam ser corrigidos para o uso de um protocolo mais seguro, como o Kerberos. As informações de log coletadas também podem auxiliar em investigações forenses após um ataque malicioso.

A autenticação NTLM e NTLMv2 é vulnerável a vários ataques, incluindo retransmissão SMB, man-in-the-middle e ataques de força bruta. Reduzir e eliminar a autenticação NTLM em um ambiente reduz o risco de um agente de ameaça obter acesso aos sistemas na rede.



Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Restrict NTLM: Outgoing NTLM traffic to remote servers



Garanta que 'Network Security: Allow PKU2U authentication requests to this computer to use online identities' esteja habilitada como 'Disabled'

Esta configuração determina se as identidades online podem ser autenticadas neste computador.

O protocolo PKU2U (usuário para usuário baseado em criptografia de chave pública) introduzido no Windows 7 e no Windows Server 2008 R2 é implementado como um SSP (provedor de suporte de segurança). O SSP permite a autenticação ponto a ponto, principalmente por meio do recurso de compartilhamento de mídia e arquivos do Windows 7 chamado HomeGroup, que permite o compartilhamento entre computadores que não são membros de um domínio.

Com o PKU2U, uma nova extensão foi introduzida no pacote de autenticação Negotiate, Spnego.dll. Nas versões anteriores do Windows, o Negotiate decidia se usaria Kerberos ou NTLM para autenticação. A extensão SSP para Negotiate, Negoexts.dll, que é tratada como um protocolo de autenticação pelo Windows, oferece suporte a SSPs da Microsoft, incluindo PKU2U.

Quando os computadores são configurados para aceitar solicitações de autenticação usando IDs online, Negoexts.dll chama o SSP PKU2U no computador usado para fazer logon. O SSP PKU2U obtém um certificado local e troca a política entre os computadores pares. Quando validado no computador peer, o certificado nos metadados é enviado ao peer de logon para validação e associa o certificado do usuário a um token de segurança e o processo de logon é concluído.

O estado recomendado para esta configuração é: Disabled .



Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network Security: Allow PKU2U authentication requests to this computer to use online identities



Resumo das configurações:
<img width="1268" height="843" alt="image" src="https://github.com/user-attachments/assets/b0545082-e344-46bb-b9a8-4f9e7598cc2b" />

<img width="1266" height="850" alt="image" src="https://github.com/user-attachments/assets/511858a2-d85f-4866-aecf-401a990b1d41" />

<img width="1265" height="847" alt="image" src="https://github.com/user-attachments/assets/10af17f0-efe5-4a42-9a52-7232617e34a1" />

<img width="1266" height="847" alt="image" src="https://github.com/user-attachments/assets/7d5b9fc1-d1d7-4d68-8dd9-61e1187e2582" />

Salve este post como parte do seu checklist de hardening Windows.
