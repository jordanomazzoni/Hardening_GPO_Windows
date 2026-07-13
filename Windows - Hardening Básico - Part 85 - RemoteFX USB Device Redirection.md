<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/15c9f35d-4a49-48f3-a90d-32b94e443166" />

# Windows - Hardening Básico - Part 85 - RemoteFX USB Device Redirection

Garanta que 'Disable Cloud Clipboard integration for server-to-client data transfer' esteja atribuido como 'Enabled'

Essa configuração de política controla se os dados transferidos da sessão remota para o cliente usando o redirecionamento da área de transferência são adicionados à área de transferência na nuvem do lado do cliente.

O estado recomendado para essa configuração é: Ativado.

Em ambientes de alta segurança, os dados da área de transferência devem permanecer locais no sistema e não devem ser sincronizados com a nuvem, pois podem conter informações confidenciais que devem ser mantidas localmente.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Connection Client\Disable Cloud Clipboard integration for server-to-client data transfer

<img width="1445" height="812" alt="image" src="https://github.com/user-attachments/assets/b79ee4cc-9afb-405a-8e68-9868de31007b" />

Garanta que 'Do not allow passwords to be saved' esteja atribuido como 'Enabled'

Essa configuração de política ajuda a impedir que clientes de Área de Trabalho Remota salvem senhas em um computador.

O estado recomendado para essa configuração é: Ativado.

Observação: se essa configuração de política foi previamente configurada como Desativada ou Não configurada, todas as senhas salvas anteriormente serão excluídas na primeira vez que um cliente de Área de Trabalho Remota se desconectar de qualquer servidor.

Um invasor com acesso físico ao computador pode conseguir burlar a proteção que resguarda as senhas salvas. Um invasor que comprometa a conta de um usuário e se conecte ao computador dele pode usar as senhas salvas para obter acesso a outros hosts.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Connection Client\Do not allow passwords to be saved

<img width="1445" height="822" alt="image" src="https://github.com/user-attachments/assets/42d21b6c-abfe-4f6d-ba8a-85d7b341817c" />

Salve este post como parte do seu checklist de hardening Windows.
