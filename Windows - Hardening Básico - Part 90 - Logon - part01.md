<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/413668ca-a71b-400a-8ca6-d25f9ce05510" />

# Windows - Hardening Básico - Part 90 - Logon - part01

Garanta que 'Block user from showing account details on sign-in' esteja atribuido como 'Enabled'

Esta política impede que o usuário exiba os detalhes da conta (endereço de e-mail ou nome de usuário) na tela de login.

O estado recomendado para esta configuração é: Ativado.

Um invasor com acesso ao console (por exemplo, alguém com acesso físico ou alguém que consiga se conectar à estação de trabalho por meio dos Serviços de Área de Trabalho Remota) poderia visualizar o nome do último usuário que fez login no servidor. O invasor poderia então tentar adivinhar a senha, usar um dicionário ou realizar um ataque de força bruta para tentar fazer login.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Block user from showing account details on sign-in

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEWAMRl8usWtA/article-inline_image-shrink_1500_2232/B4DZ4s_TykHoBE-/0/1778871254533?e=1785369600&v=beta&t=gZkr1r1TZdvu1N3bFo-uUzH8HlVxUgYZkiK_b_K6VjQ)

Garanta que 'Do not display network selection UI' esteja atribuido como 'Enabled'

Essa configuração de política permite controlar se qualquer pessoa pode interagir com a interface de usuário de redes disponíveis na tela de logon.

O estado recomendado para essa configuração é: Ativado.

Um usuário não autorizado pode desconectar o computador da rede ou conectá-lo a outras redes disponíveis sem fazer logon no Windows.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface de usuário como Ativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Do not display the network selection UI

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQHdK5XoHbDrDw/article-inline_image-shrink_1500_2232/B4DZ4s_X6hHoAQ-/0/1778871271450?e=1785369600&v=beta&t=2ZHDWyONFll5Wxz3Yfy7Ujo63f5bt6txGS5sEw2TeLs)

Garanta que 'Do not enumerate connected users on domain-joined computers' esteja atribuido como 'Enabled'

Essa configuração de política impede que usuários conectados sejam enumerados em computadores ingressados no domínio.

O estado recomendado para essa configuração é: Ativado.

Um agente malicioso poderia usar esse recurso para coletar nomes de contas de outros usuários. Essas informações poderiam ser usadas em conjunto com outros tipos de ataques, como adivinhação de senhas ou engenharia social. O valor dessa contramedida é pequeno, pois um usuário com credenciais de domínio poderia coletar as mesmas informações de conta usando outros métodos.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Do not enumerate connected users on domain-joined computers

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQE0a-FTxiZmVw/article-inline_image-shrink_1000_1488/B4DZ4s_bR3KMAM-/0/1778871285264?e=1785369600&v=beta&t=ldjqYRzd162Vth8m2bzrq1bXxhmC-KAEULPWnCwj5fs)

Salve este post como parte do seu checklist de hardening Windows.
