<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/85550cbc-98dd-4662-b65b-6b60751c0910" />


# Windows - Hardening Básico - Part 24 - Firewall - Private Profile

O Private Profile é destinado a redes onde o usuário ou o administrador designou explicitamente como "Privada" (uma rede doméstica por exemplo). 

O Domain Profile (Perfil de Domínio), é ativado automaticamente quando o computador detecta que está conectado a uma rede onde ele consegue autenticar-se com um Domain Controller (DC) do Active Directory.

Habilitar o Windows Firewall não é uma prática fora de moda. É o desdobramento da estratégia de microssegregação de rede e a primeira barreira real contra a movimentação lateral de ameaças. Em um cenário onde o perímetro corporativo tradicional desapareceu, cada host deve atuar como sua própria fortaleza (somando camadas com EDR e outros).

 Garanta que a configuração 'Windows Firewall: Private: Firewall state' esteja atribuída como 'On (recommended)' 

Se o firewall estiver desligado, todo o tráfego poderá acessar o sistema, e um agente de ameaça poderá explorar remotamente uma fraqueza em um serviço de rede.

Garanta que a configuração 'Windows Firewall: Private: Inbound connections' esteja atribuída como 'Block (default)' 

Se o firewall permitir que todo o tráfego acesse o sistema, um agente de ameaça poderá explorar remotamente uma fraqueza em um serviço de rede.

Garanta que a configuração 'Windows Firewall: Private: Settings: Display a notification' esteja atribuída como 'No' 

Quando a configuração Aplicar regras de firewall locais estiver definida como Não , é recomendável definir também a configuração Exibir uma notificação como Não . Caso contrário, os usuários continuarão recebendo mensagens perguntando se desejam desbloquear uma conexão de entrada restrita, mas a resposta do usuário será ignorada.

Garanta que a configuração 'Windows Firewall: Private: Logging: Name' esteja atribuída

Caminho sugerido:

%systemroot%\system32\logfiles\firewall\privatefw.log

Se os eventos do Firewall do Windows não forem registrados, poderá ser difícil ou impossível para os administradores analisarem problemas do sistema ou atividades não autorizadas de agentes de ameaças.

A Microsoft armazena todos os eventos de firewall como um arquivo no sistema ( pfirewall.log ). Para melhorar o registro em log, separe cada perfil de firewall (domínio, privado, público) em seu próprio arquivo de log distinto (privatefw.log, privatefw.log, publicfw.log) para melhor organização e identificação de problemas específicos em cada perfil.

Garanta que a configuração 'Windows Firewall: Private: Logging: Size limit (KB)' esteja atribuída como '16,384 KB or greater' 

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

Garanta que a configuração 'Windows Firewall: Private: Logging: Log dropped packets' esteja atribuída como 'Yes' 

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

Garanta que a configuração 'Windows Firewall: Private: Logging: Log successful connections' esteja atribuída como 'Yes'

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Windows Defender Firewall with Advanced Security\Windows Defender Firewall with Advanced Security\Windows Defender Firewall Properties\Private Profile

<img width="1088" height="571" alt="image" src="https://github.com/user-attachments/assets/714abc29-1332-4fd6-a16b-fa27ce832ead" />

<img width="1074" height="578" alt="image" src="https://github.com/user-attachments/assets/88105e85-34d6-408e-8557-e9f8a0473579" />

<img width="1102" height="643" alt="image" src="https://github.com/user-attachments/assets/92390938-4fad-495e-a3aa-723d0f100be0" />

Salve este post como parte do seu checklist de hardening Windows.

Ativar o firewall é o ato de erguer o escudo, habilitar os logs de firewall é o que nos dá olhos para enxergar os rastros deixados pelo inimigo. Um firewall sem logs é um componente mudo. Ele bloqueia a ameaça, mas priva o time de SOC e GRC de entender a origem, a técnica e a recorrência da tentativa de intrusão. 

Transformar esses logs em evidências auditáveis é o que separa um parque computacional passivo de uma infraestrutura tecnicamente governada e resiliente.
