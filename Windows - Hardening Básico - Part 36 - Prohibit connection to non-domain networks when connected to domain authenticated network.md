<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/7c28e789-42c1-4f08-a8de-32a1a8bc61ac" />


# Windows - Hardening Básico - Part 36 - Prohibit connection to non-domain networks when connected to domain authenticated network

Essa configuração de política impede que os computadores se conectem simultaneamente a uma rede baseada em domínio e a uma rede não baseada em domínio. A possível preocupação é que um usuário, sem saber, permita o fluxo de tráfego de rede entre a rede pública insegura e a rede gerenciada pela empresa.

O computador responde às tentativas de conexão de rede automáticas e manuais com base nas seguintes circunstâncias:

Tentativas de conexão automáticas: 

Quando o computador já está conectado a uma rede baseada em domínio, todas as tentativas de conexão automáticas a redes não baseadas em domínio são bloqueadas. 
Quando o computador já está conectado a uma rede não baseada em domínio, as tentativas de conexão automática a redes baseadas em domínio são bloqueadas.

Tentativas de conexão manuais: 

Quando o computador já está conectado a uma rede não baseada em domínio ou a uma rede baseada em domínio por meio de uma mídia diferente de Ethernet, e um usuário tenta criar uma conexão manual a uma rede adicional em violação a essa configuração de política, a conexão de rede existente é desconectada e a conexão manual é permitida. 
Quando o computador já está conectado a uma rede não baseada em domínio ou a uma rede baseada em domínio via Ethernet, e um usuário tenta criar uma conexão manual a uma rede adicional que viole esta configuração de política, a conexão Ethernet existente é mantida e a tentativa de conexão manual é bloqueada.

Garanta que 'Prohibit connection to non-domain networks when connected to domain authenticated network' esteja atribuido como 'Enabled'
Computer Configuration\Policies\Administrative Templates\Network\Windows Connection Manager\Prohibit connection to non-domain networks when connected to domain authenticated network

<img width="1277" height="864" alt="image" src="https://github.com/user-attachments/assets/ecdcfdb4-eee4-4286-9c9c-e5cc9082d38c" />

Salve este post como parte do seu checklist de hardening Windows.
