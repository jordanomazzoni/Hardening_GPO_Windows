<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/ba5617e9-6d05-4f01-8249-167604e67361" />

# Windows - Hardening Básico - Part 88 - User Rights Assignment - part03

Garanta que 'Deny log on locally' esteja atribuido como 'Guests'

Essa configuração de segurança determina quais usuários serão impedidos de fazer logon no computador. Esta configuração de política substitui a configuração de política Permitir logon local se uma conta estiver sujeita a ambas as políticas.

O estado recomendado para esta configuração é incluir: Convidados .

Importante: Se você aplicar esta política de segurança ao grupo Todos, ninguém poderá fazer logon localmente.

Qualquer conta com capacidade de fazer logon localmente pode ser usada para fazer logon no console do computador. Se esse direito de usuário não estiver restrito a usuários legítimos que precisam fazer logon no console do computador, usuários não autorizados poderão baixar e executar software mal-intencionado que aumente seus privilégios.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para incluir convidados:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Deny log on locally

<img width="1419" height="824" alt="image" src="https://github.com/user-attachments/assets/b0fa39ab-f896-40e7-8819-c55497265f08" />

Garanta que 'Deny log on through Remote Desktop Services' esteja atribuido como 'Guests, Local account' 

Esta configuração de política determina se os usuários podem fazer logon como clientes de Área de Trabalho Remota. Após a estação de trabalho de linha de base ser associada a um ambiente de domínio, não há necessidade de usar contas locais para acessar a estação de trabalho pela rede. As contas de domínio podem acessar a estação de trabalho para administração e processamento do usuário final. Este direito de usuário substitui o direito de usuário Permitir logon por meio dos Serviços de Área de Trabalho Remota se uma conta estiver sujeita a ambas as políticas.

O estado recomendado para esta configuração é incluir: Convidados, Conta local

Qualquer conta com direito de fazer logon por meio dos Serviços de Área de Trabalho Remota pode ser usada para fazer logon no console remoto do computador. Se esse direito de usuário não estiver restrito a usuários legítimos que precisam fazer logon no console do computador, usuários não autorizados poderão baixar e executar software mal-intencionado que aumente seus privilégios.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho da UI para incluir Convidados, Conta local:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Deny log on through Remote Desktop Services

<img width="1438" height="825" alt="image" src="https://github.com/user-attachments/assets/d498a22d-c753-4ca2-9298-88522270afc7" />

Garanta que 'Restore files and directories' esteja atribuido como 'Administrators'

Essa configuração de política determina quais usuários podem ignorar permissões de arquivos, diretórios, registros e outras permissões de objetos persistentes ao restaurar arquivos e diretórios de backup em sistemas que executam o Windows Vista (ou mais recente).

Este direito de usuário também determina quais usuários podem definir entidades de segurança válidas como proprietários de objetos; é semelhante ao direito de usuário Fazer backup de arquivos e diretórios.

O estado recomendado para esta configuração é: Administrators .

Nota: Este direito de usuário é considerado um “privilégio confidencial” para fins de auditoria.

Um agente de ameaça com o direito de usuário Restaurar arquivos e diretórios pode restaurar dados confidenciais em um computador e substituir dados mais recentes, o que pode levar à perda de dados importantes, corrupção de dados ou negação de serviço (DoS).

Os agentes de ameaças podem substituir arquivos executáveis usados por administradores legítimos ou serviços de sistema por versões que incluem software mal-intencionado para conceder privilégios elevados, comprometer dados ou instalar backdoors para acesso contínuo ao computador.

Nota: Mesmo que a contramedida a seguir esteja configurada, um agente de ameaça ainda poderá restaurar dados para um computador em um domínio controlado pelo agente. Portanto, é fundamental que as organizações protejam cuidadosamente a mídia usada para fazer backup dos dados.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para Administrators :

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Restore files and directories

<img width="1430" height="828" alt="image" src="https://github.com/user-attachments/assets/b01539ca-0730-42cb-8af2-7bce4736f0fb" />

Garanta que 'Shut down the system' esteja atribuido como 'Administrators, Users'

Essa configuração de política determina quais usuários conectados localmente nos computadores do seu ambiente podem encerrar o sistema operacional com o comando Desligar. O uso indevido deste direito do usuário pode resultar em uma condição de negação de serviço (DoS).

O estado recomendado para esta configuração é: Administradores, Usuários.

A capacidade de desligar uma estação de trabalho deve estar disponível geralmente para administradores e usuários autorizados dessa estação de trabalho, mas não deve ser permitida para convidados ou usuários não autorizados para evitar um ataque DoS.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para Administradores, Usuários:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Shut down the system

<img width="1431" height="828" alt="image" src="https://github.com/user-attachments/assets/7b650864-f1af-4c85-851f-fd472bb4b875" />

Salve este post como parte do seu checklist de hardening Windows.
