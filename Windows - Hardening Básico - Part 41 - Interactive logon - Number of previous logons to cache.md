<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/d86377c6-92ce-40dc-8b20-e3078588c6f3" />


# Windows - Hardening Básico - Part 41 - Interactive logon - Number of previous logons to cache

Aqui estamos limitando a quantidade de hashes que o LSA (Local Security Authority) armazena localmente. Esta configuração inibe principalmente T1003.005 - OS Credential Dumping: Cached Domain Credentials. Se um atacante ganha privilégios de SYSTEM ou Local Admin, ele pode usar ferramentas como Mimikatz, Impacket ou Hashcat para extrair esses hashes. Se o valor padrão (geralmente 10) estiver ativo, o atacante tem 10 chances de encontrar uma senha "quebrável". Com 4 ou menos, você reduz a superfície de exposição em mais de 60%.

Garanta que 'Interactive logon: Number of previous logons to cache (in case domain controller is not available)' esteja atribuido como '4 or fewer logon(s)'

Essa configuração de política determina se um usuário pode fazer logon em um domínio do Windows usando informações de conta armazenadas em cache. As informações de logon para contas de domínio podem ser armazenadas em cache localmente para permitir que os usuários façam logon mesmo que não seja possível contatar um Controlador de Domínio.

O estado recomendado para essa configuração é: 4 ou menos logons.

Observação: o número atribuído a essa configuração de política indica a quantidade de usuários cujas informações de logon o computador armazenará em cache localmente. Se o número for definido como 4, o computador armazenará em cache as informações de logon de 4 usuários. Quando um 5º usuário fizer logon no computador, o servidor sobrescreverá a sessão de logon em cache mais antiga.

Os usuários que acessarem o console do computador terão suas credenciais de logon armazenadas em cache nesse computador. Um invasor que consiga acessar o sistema de arquivos do computador poderá localizar essas informações em cache e usar um ataque de força bruta para tentar descobrir as senhas dos usuários. Para mitigar esse tipo de ataque, o Windows criptografa as informações e oculta sua localização física.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Interactive logon: Number of previous logons to cache (in case domain controller is not available)

<img width="1264" height="735" alt="image" src="https://github.com/user-attachments/assets/81faf312-f613-41d6-aee3-5e538e35f4ed" />

Os usuários não poderão fazer login em nenhum computador se não houver um Controlador de Domínio disponível para autenticá-los. As organizações podem configurar esse valor para 2 nos computadores dos usuários finais, especialmente para usuários móveis. Um valor de configuração 2 significa que as informações de login do usuário permanecerão no cache, mesmo que um membro da equipe de TI tenha feito login recentemente no computador para realizar manutenção do sistema. Esse método permite que os usuários façam login em seus computadores quando não estiverem conectados à rede da organização.

Em uma rede local cabeada, onde a conectividade com o Domain Controller (DC) é presumidamente estável, essa configuração pode fazer sentido para o seu contexto. É comum que um usuário membro do grupo Domain Admins logue em uma estação para uma manutenção rápida. Com o valor padrão (10), o hash permanece vulnerável por semanas. Com o valor 0, assim que o Admin faz logoff, a credencial dele desaparece da máquina física. Para Notebooks Corporativos você pode experimentar definir como 1 ou 2 atingindo um equilibiro permitindo logon em viagens ou home office com algum nível de segurança.
