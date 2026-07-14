<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/9d691abc-0511-4872-b6f2-ff5c37bf8571" />


# Windows - Hardening Básico - Part 66 - Temporary folders - RSS Feeds

Garanta que 'Do not delete temp folders upon exit' esteja atribuido como 'Disabled'

Essa configuração de política especifica se os Serviços de Área de Trabalho Remota mantêm as pastas temporárias por sessão do usuário após o logout.

O estado recomendado para essa configuração é: Desativado.

Informações confidenciais podem estar contidas nas pastas temporárias e visíveis para outros administradores que acessarem o sistema.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Temporary Folders\Do not delete temp folders upon exit

<img width="1264" height="844" alt="image" src="https://github.com/user-attachments/assets/2301688f-ec26-4812-bc41-de6a7994ee24" />

Garanta que 'Prevent downloading of enclosures' esteja atribuido como 'Enabled'

Essa configuração de política impede que o usuário baixe arquivos anexos (arquivos anexados) de um feed RSS para o seu computador.

O estado recomendado para essa configuração é: Ativado.

Permitir o download de anexos por meio do feed RSS pode introduzir arquivos com intenções maliciosas.

Computer Configuration\Policies\Administrative Templates\Windows Components\RSS Feeds\Prevent downloading of enclosures

<img width="1263" height="848" alt="image" src="https://github.com/user-attachments/assets/6101d7fb-cf91-4a5e-ad77-8d55d91f839e" />

Salve este post como parte do seu checklist de hardening Windows.
