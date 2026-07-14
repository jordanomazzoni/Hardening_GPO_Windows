<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/25760dde-2a47-4322-8b67-490f4cd6b897" />

# Windows - Hardening Básico - Part 78 - Printers - part01

Garanta que 'Configure Redirection Guard' esteja atribuido como 'Enabled: Redirection Guard Enabled'

Essa configuração de política determina se a Proteção de Redirecionamento está habilitada para o spooler de impressão. A Proteção de Redirecionamento pode impedir que redirecionamentos de arquivos sejam usados no spooler de impressão.

O estado recomendado para essa configuração é: Habilitado: Proteção de Redirecionamento Habilitada.

Essa configuração impede que usuários sem privilégios de administrador redirecionem arquivos no processo do spooler de impressão.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Habilitado: Proteção de Redirecionamento Habilitada.

Computer Configuration\Policies\Administrative Templates\Printers\Configure Redirection Guard 

<img width="1441" height="814" alt="image" src="https://github.com/user-attachments/assets/b85e84d1-4388-492c-b41c-d9a65d26590a" />

Garanta que 'Configure RPC connection settings: Protocol to use for outgoing RPC connections' esteja atribuido como 'Enabled: RPC over TCP'

Essa configuração de política controla qual protocolo e quais configurações de protocolo usar para conexões de Chamada de Procedimento Remoto (RPC) de saída para um servidor de spooler de impressão remoto.

O estado recomendado para essa configuração é: Ativado: RPC sobre TCP

Essa configuração impede o uso de pipes nomeados para conexões RPC com o servidor de spooler de impressão e força o uso de TCP, que é um método de comunicação mais seguro.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: RPC sobre TCP:

Computer Configuration\Policies\Administrative Templates\Printers\Configure RPC connection settings: Protocol to use for outgoing RPC connections

<img width="1444" height="852" alt="image" src="https://github.com/user-attachments/assets/2c4cb052-f4a1-45b5-aabe-5e80d9932aaa" />

Garanta que 'Configure RPC connection settings: Use authentication for outgoing RPC connections' esteja atribuido como 'Enabled: Default'

Essa configuração de política controla qual protocolo e quais configurações de protocolo usar para conexões RPC (Chamada de Procedimento Remoto) de saída para um spooler de impressão remoto.

O estado recomendado para essa configuração é: Ativado: Padrão

Essa configuração pode impedir o uso de pipes nomeados para conexões RPC com o spooler de impressão e força o uso de TCP, que é um método de comunicação mais seguro.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Padrão:

Computer Configuration\Policies\Administrative Templates\Printers\Configure RPC connection settings: Use authentication for outgoing RPC connections

<img width="1444" height="852" alt="image" src="https://github.com/user-attachments/assets/0dcdb229-19b2-4272-ba98-6d5e42006df5" />

Salve este post como parte do seu checklist de hardening Windows.
