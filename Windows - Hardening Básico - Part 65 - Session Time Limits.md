<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/5243434f-85dd-435c-93c8-c590f92b1735" />


# Windows - Hardening Básico - Part 65 - Session Time Limits

Garanta que 'Set time limit for active but idle Remote Desktop Services sessions' esteja atribuida como 'Enabled: 15 minutes or less, but not Never (0)'

Essa configuração de política permite especificar o tempo máximo que uma sessão ativa dos Serviços de Área de Trabalho Remota pode ficar ociosa (sem interação do usuário) antes de ser desconectada automaticamente.

O estado recomendado para essa configuração é: Ativado: 15 minutos ou menos, mas não Nunca (0).

Essa configuração ajuda a evitar que sessões ativas da Área de Trabalho Remota ocupem o computador por longos períodos enquanto não estão em uso, impedindo que os recursos de computação sejam consumidos por um grande número de sessões inativas. Além disso, sessões antigas e esquecidas da Área de Trabalho Remota que ainda estejam ativas podem causar bloqueios de senha se a senha do usuário tiver sido alterada, mas a sessão antiga ainda estiver em execução. Para sistemas que limitam o número de usuários conectados (por exemplo, servidores no modo Administrativo padrão - apenas 2 sessões), sessões antigas, mas ainda ativas, de outros usuários podem impedir que outro usuário se conecte, resultando em uma negação de serviço efetiva.

Além disso, tempos limite de sessão mal configurados ou definidos para um longo período podem deixar o sistema vulnerável a ataques de sequestro de sessão por parte de invasores.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Session Time Limits\Set time limit for active but idle Remote Desktop Services sessions

<img width="1265" height="845" alt="image" src="https://github.com/user-attachments/assets/8fdf2d55-f7c6-4cc9-980f-7fc8a405cd00" />

Garanta que 'Set time limit for disconnected sessions' esteja atribuida como 'Enabled: 1 minute'

Essa configuração de política permite definir um limite de tempo para sessões desconectadas dos Serviços de Área de Trabalho Remota.

O estado recomendado para essa configuração é: Ativado: 1 minuto.

Essa configuração ajuda a evitar que sessões ativas da Área de Trabalho Remota ocupem o computador por longos períodos enquanto não estão em uso, impedindo que os recursos de computação sejam consumidos por um grande número de sessões desconectadas, mas ainda ativas. Além disso, sessões antigas e esquecidas da Área de Trabalho Remota que ainda estão ativas podem causar bloqueios de senha se a senha do usuário tiver sido alterada, mas a sessão antiga ainda estiver em execução. Para sistemas que limitam o número de usuários conectados (por exemplo, servidores no modo Administrativo padrão - apenas 2 sessões), sessões antigas, mas ainda ativas, de outros usuários podem impedir que outro usuário se conecte, resultando em uma negação de serviço efetiva. Essa configuração é importante para garantir que uma sessão desconectada seja encerrada corretamente.

Além disso, tempos limite de sessão mal configurados ou definidos para um longo período podem deixar o sistema vulnerável a ataques que sequestrem a sessão.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Session Time Limits\Set time limit for disconnected sessions

<img width="1263" height="843" alt="image" src="https://github.com/user-attachments/assets/d7c2297e-69c2-4b74-9ab9-0c24911dc079" />

Salve este post como parte do seu checklist de hardening Windows.
