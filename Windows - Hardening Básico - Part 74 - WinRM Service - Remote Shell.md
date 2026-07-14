<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f6f27253-4426-4b03-ae6a-d84f21d9cfa5" />


# Windows - Hardening Básico - Part 74 - WinRM Service - Remote Shell

Garanta que 'Allow remote server management through WinRM' esteja atribuido como 'Disabled'

Essa configuração de política permite gerenciar se o serviço de Gerenciamento Remoto do Windows (WinRM) escuta automaticamente na rede por solicitações no transporte HTTP pela porta HTTP padrão.

O estado recomendado para essa configuração é: Desativado.

Qualquer recurso é uma potencial via de ataque; aqueles que permitem conexões de rede de entrada são particularmente arriscados. Habilite o uso do serviço de Gerenciamento Remoto do Windows (WinRM) somente em redes confiáveis e, quando possível, utilize controles adicionais, como IPsec.

Computer Configuration\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Service\Allow remote server management through WinRM

<img width="1261" height="837" alt="image" src="https://github.com/user-attachments/assets/e62a4add-8242-4ae1-8153-6f8baeae5db2" />

Garanta que 'Allow Remote Shell Access' esteja atribuido como 'Disabled'

Essa configuração de política permite gerenciar a configuração de acesso remoto a todos os shells compatíveis para executar scripts e comandos.

O estado recomendado para essa configuração é: Desativado.

Observação: o texto de ajuda do GPME para essa configuração está redigido incorretamente, dando a entender que configurá-la como Ativada rejeitará novas conexões de Shell Remoto e configurá-la como Desativada permitirá conexões de Shell Remoto. O oposto é verdadeiro (e está de acordo com o nome da configuração). Trata-se de um erro de redação da Microsoft no Modelo Administrativo.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Shell\Allow Remote Shell Access

<img width="1264" height="841" alt="image" src="https://github.com/user-attachments/assets/6147a840-11b2-4e99-bff7-1694b7fdd947" />

Salve este post como parte do seu checklist de hardening Windows.
