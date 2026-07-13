<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/c8665f6e-73b2-40f5-9934-c0c0d3fefdfb" />

# Windows - Hardening Básico - Part 86 - User Rights Assignment - part01

Garanta que 'Access this computer from the network' esteja atribuido como 'Administrators, Remote Desktop Users' 

Essa configuração de política permite que outros usuários na rede se conectem ao computador e é exigida por vários protocolos de rede que incluem protocolos baseados em Server Message Block (SMB), NetBIOS, Common Internet File System (CIFS) e Component Object Model Plus (COM+).

O estado recomendado para esta configuração é: Administradores, Usuários de Área de Trabalho Remota.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para Administradores, Usuários de Área de Trabalho Remota:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Access this computer from the network

<img width="1427" height="812" alt="image" src="https://github.com/user-attachments/assets/18dbaad1-29be-49f7-8da2-b464fc1df040" />

Garanta que 'Allow log on locally' esteja atribuido como 'Administrators, Users' 

Essa configuração de política determina quais usuários podem fazer logon interativamente nos computadores do seu ambiente. Os logons iniciados pressionando a sequência de teclas CTRL+ALT+DEL no teclado do computador cliente exigem esse direito de usuário. Os usuários que tentam fazer logon por meio de Serviços de Terminal/Serviços de Área de Trabalho Remota ou IIS também exigem esse direito de usuário.

O estado recomendado para esta configuração é: Administradores, Usuários.

Qualquer conta com o direito de usuário Permitir logon local pode fazer logon no console do computador. Se você não restringir esse direito de usuário a usuários legítimos que precisam fazer logon no console do computador, usuários não autorizados poderão baixar e executar software mal-intencionado para elevar seus privilégios.

Se você remover esses grupos padrão, poderá limitar as habilidades dos usuários designados a funções administrativas específicas em seu ambiente. Você deve confirmar que as atividades delegadas não serão afetadas negativamente por quaisquer alterações feitas no direito de usuário Permitir logon local.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para Administradores, Usuários:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Allow log on locally

<img width="1428" height="775" alt="image" src="https://github.com/user-attachments/assets/d510dcea-0bb5-49e2-b1c9-de5da7b326c9" />

Garanta que 'Back up files and directories' esteja atribuido como 'Administrators'

Essa configuração de política permite que os usuários contornem as permissões de arquivos e diretórios para fazer backup do sistema. Este direito de usuário é habilitado somente quando um aplicativo (como NTBACKUP) tenta acessar um arquivo ou diretório por meio da interface de programação de aplicativo (API) de backup do sistema de arquivos NTFS. Caso contrário, as permissões de arquivo e diretório atribuídas serão aplicadas.

O estado recomendado para esta configuração é: Administrators .

Os usuários que conseguem fazer backup de dados de um computador podem levar a mídia de backup para um computador que não seja do domínio no qual tenham privilégios administrativos e restaurar os dados. Eles poderiam apropriar-se dos arquivos e visualizar quaisquer dados não criptografados contidos no conjunto de backup.

As alterações na associação dos grupos que possuem o direito de usuário Fazer backup de arquivos e diretórios podem limitar as habilidades dos usuários designados a funções administrativas específicas em seu ambiente. Você deve confirmar se os administradores de backup autorizados ainda podem realizar operações de backup.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho da UI para Administrators .

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Back up files and directories

<img width="1431" height="792" alt="image" src="https://github.com/user-attachments/assets/ad4b96cf-adae-40b7-bbf9-6f375bd26626" />

Salve este post como parte do seu checklist de hardening Windows.
