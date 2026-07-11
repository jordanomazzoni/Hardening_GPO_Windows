<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/ace541c0-0b9b-476d-ad8e-9776aa169771" />


# Windows - Hardening Básico - Part 93 - Windows Ink Workspace + Windows Installer

Garanta que 'Allow suggested apps in Windows Ink Workspace' esteja atribuido como 'Disabled'

Essa configuração de política determina se os aplicativos sugeridos no Windows Ink Workspace são permitidos.

O estado recomendado para essa configuração é: Desativado.

Esse recurso da Microsoft foi projetado para coletar dados e sugerir aplicativos com base nesses dados coletados. Desativar essa configuração ajudará a garantir que seus dados não sejam compartilhados com terceiros.

Para definir a configuração recomendada por meio da Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:

Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Ink Workspace\\Allow suggested apps in Windows Ink Workspace

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQHLl60BF_oL6w/article-inline_image-shrink_1000_1488/B4DZ4tHvRsHgAI-/0/1778873464297?e=1785369600&v=beta&t=wji9ucCC94oAat-SIXAQWiYIIl8McWRooswQRZtbYdM)

Garanta que 'Allow Windows Ink Workspace' esteja atribuido como 'Enabled: On, but disallow access above lock' OR 'Enabled: Disabled'

Essa configuração de política determina se os itens do Windows Ink podem ser acessados acima da tela de bloqueio.

O estado recomendado para essa configuração é: Ativado: Ligado, mas impedir o acesso acima do bloqueio OU Ativado: Desativado.

Não é recomendável permitir o acesso a aplicativos com o sistema bloqueado. Se esse recurso for permitido, ele só deverá estar acessível após a autenticação do usuário com as credenciais corretas.

Para definir a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Ligado, mas impedir o acesso acima do bloqueio OU Ativado: Desativado:

Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Ink Workspace\\Allow Windows Ink Workspace

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQF5RGFUJqyNwg/article-inline_image-shrink_1500_2232/B4DZ4tHZMBKEAQ-/0/1778873373809?e=1785369600&v=beta&t=U-wcsBFvo7ZGAFcYJzr7p_4Ym12GVfMBv_v0ycD-BAo)

Garanta que 'Prevent Internet Explorer security prompt for Windows Installer scripts' esteja atribuido como 'Disabled'

Essa configuração de política controla se os programas baseados na Web podem instalar software no computador sem notificar o usuário.

O estado recomendado para essa configuração é: Desativado.

Suprimir o aviso do sistema pode representar um risco de segurança e aumentar a superfície de ataque do sistema.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:

Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Installer\\Prevent Internet Explorer security prompt for Windows Installer scripts

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEC0OdBbJxyrw/article-inline_image-shrink_1500_2232/B4DZ4tHTw9I0AQ-/0/1778873351602?e=1785369600&v=beta&t=qtwWaF4joUZkrDMhHctzzvgMyyc0rDCXAXYJXSWUzj4)

Salve este post como parte do seu checklist de hardening Windows.
