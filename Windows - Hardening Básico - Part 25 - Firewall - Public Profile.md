<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/54f53de3-2a93-4305-acf0-eef2145b8e14" />


# Windows - Hardening Básico - Part 25 - Firewall - Public Profile

O Public Profile é projetado para redes onde você conhece e confia nos outros dispositivos conectados (como sua casa ou um escritório pequeno).

Garanta que a configuração 'Windows Firewall: Public: Firewall state' esteja atribuída como 'On (recommended)' 

Garanta que a configuração 'Windows Firewall: Public: Inbound connections' esteja atribuída como 'Block (default)' 

Garanta que a configuração 'Windows Firewall: Public: Settings: Display a notification' esteja atribuída como 'No' 

Garanta que a configuração 'Windows Firewall: Public: Settings: Apply local firewall rules' esteja atribuída como 'No' 

Garanta que a configuração 'Windows Firewall: Public: Settings: Apply local connection security rules' esteja atribuída como 'No' 

Garanta que a configuração 'Windows Firewall: Public: Logging: Name' esteja atribuída

Garanta que a configuração 'Windows Firewall: Public: Logging: Size limit (KB)' esteja atribuída como '16,384 KB or greater' 

Garanta que a configuração 'Windows Firewall: Public: Logging: Log dropped packets' esteja atribuída como 'Yes' 

Garanta que a configuração 'Windows Firewall: Public: Logging: Log successful connections' esteja atribuída como 'Yes'

O que temos de diferente para este Profile:

Windows Firewall: Public: Settings: Apply local firewall rules

Esta configuração controla se os administradores locais têm permissão para criar regras de firewall locais que se aplicam junto com as regras de firewall configuradas pela Política de Grupo. Recomendado para esta configuração é: Não .

Windows Firewall: Public: Settings: Apply local connection security rules

Esta configuração controla se os administradores locais têm permissão para criar regras de segurança de conexão que se aplicam junto com as regras de segurança de conexão configuradas pela Política de Grupo. Recomendado para esta configuração é: Não .

Sugestão para caminho e nome do arquivo de logs:

%SystemRoot%\System32\logfiles\firewall\publicfw.log

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Windows Defender Firewall with Advanced Security\Windows Defender Firewall with Advanced Security\Windows Defender Firewall Properties\Public Profile

<img width="1100" height="639" alt="image" src="https://github.com/user-attachments/assets/555e543e-7eec-4491-b47d-d82459ff5793" />

<img width="1096" height="636" alt="image" src="https://github.com/user-attachments/assets/0f78e82d-536e-46dc-8c6f-9ae749cafc53" />

<img width="1097" height="677" alt="image" src="https://github.com/user-attachments/assets/f7be6595-6d32-49f5-bc46-e0df9f432a99" />

Salve este post como parte do seu checklist de hardening Windows.

Ativar o firewall é o ato de erguer o escudo, habilitar os logs de firewall é o que nos dá olhos para enxergar os rastros deixados pelo inimigo. Um firewall sem logs é um componente mudo. Ele bloqueia a ameaça, mas priva o time de SOC e GRC de entender a origem, a técnica e a recorrência da tentativa de intrusão. 

Transformar esses logs em evidências auditáveis é o que separa um parque computacional passivo de uma infraestrutura tecnicamente governada e resiliente.
