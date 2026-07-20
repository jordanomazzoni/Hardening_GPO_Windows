<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/783b4437-b908-4edc-88d9-7487ab6b11d7" />


# Windows - Hardening Básico - Part 23 - Firewall - Domain Profile

Habilitar o Windows Firewall não é uma prática fora de moda. É o desdobramento da estratégia de microssegregação de rede e a primeira barreira real contra a movimentação lateral de ameaças. Em um cenário onde o perímetro corporativo tradicional desapareceu, cada host deve atuar como sua própria fortaleza (somando camadas com EDR e outros).

 Garanta que a configuração 'Windows Firewall: Domain: Firewall state' esteja atribuída como 'On (recommended)' 

Se o firewall estiver desligado, todo o tráfego poderá acessar o sistema, e um agente de ameaça poderá explorar remotamente uma fraqueza em um serviço de rede.

Garanta que a configuração 'Windows Firewall: Domain: Inbound connections' esteja atribuída como 'Block (default)' 

Se o firewall permitir que todo o tráfego acesse o sistema, um agente de ameaça poderá explorar remotamente uma fraqueza em um serviço de rede.

Garanta que a configuração 'Windows Firewall: Domain: Settings: Display a notification' esteja atribuída como 'No' 

Quando a configuração Aplicar regras de firewall locais estiver definida como Não , é recomendável definir também a configuração Exibir uma notificação como Não . Caso contrário, os usuários continuarão recebendo mensagens perguntando se desejam desbloquear uma conexão de entrada restrita, mas a resposta do usuário será ignorada.

Garanta que a configuração 'Windows Firewall: Domain: Logging: Name' esteja atribuída

Caminho sugerido:

%SystemRoot%\System32\logfiles\firewall\domainfw.log 

Se os eventos do Firewall do Windows não forem registrados, poderá ser difícil ou impossível para os administradores analisarem problemas do sistema ou atividades não autorizadas de agentes de ameaças.

A Microsoft armazena todos os eventos de firewall como um arquivo no sistema ( pfirewall.log ). Para melhorar o registro em log, separe cada perfil de firewall (domínio, privado, público) em seu próprio arquivo de log distinto (domainfw.log, privatefw.log, publicfw.log) para melhor organização e identificação de problemas específicos em cada perfil.

Garanta que a configuração 'Windows Firewall: Domain: Logging: Size limit (KB)' esteja atribuída como '16,384 KB or greater' 

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

Garanta que a configuração 'Windows Firewall: Domain: Logging: Log dropped packets' esteja atribuída como 'Yes' 

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

Garanta que a configuração 'Windows Firewall: Domain: Logging: Log successful connections' esteja atribuída como 'Yes'

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Windows Defender Firewall with Advanced Security\Windows Defender Firewall with Advanced Security\Windows Defender Firewall Properties\Domain Profile

<img width="1098" height="548" alt="image" src="https://github.com/user-attachments/assets/0e3c7d7b-4464-438c-9c61-335ef080215a" />

<img width="1093" height="585" alt="image" src="https://github.com/user-attachments/assets/04fb9194-eb16-4dfb-9365-8611b3b85539" />

<img width="1100" height="659" alt="image" src="https://github.com/user-attachments/assets/27f90519-3428-4a71-a0fa-78feaf910030" />

Salve este post como parte do seu checklist de hardening Windows.

Ativar o firewall é o ato de erguer o escudo, habilitar os logs de firewall é o que nos dá olhos para enxergar os rastros deixados pelo inimigo. Um firewall sem logs é um componente mudo. Ele bloqueia a ameaça, mas priva o time de SOC e GRC de entender a origem, a técnica e a recorrência da tentativa de intrusão. 

Transformar esses logs em evidências auditáveis é o que separa um parque computacional passivo de uma infraestrutura tecnicamente governada e resiliente.
