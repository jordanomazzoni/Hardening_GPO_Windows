<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/1f98027c-44b4-4d63-b1e1-bbe3999b8860" />


# Hardening Básico - Part 01 - Remote Assistance

O Remote Assistance no Windows é um vetor comum em ataques internos. Neste guia, mostro como desativá-lo via GPO, e por que isso deve estar no seu checklist de hardening.

A funcionalidade permite visualizar ou controlar remotamente um computador Windows através de uma rede ou ligação à Internet para resolver problemas sem acesso físico. Está disponível em todas as edições do Windows 10 e Windows 11, incluindo a edição Home.

Certifique-se de que a opção 'Configure Offer Remote Assistance' esteja definida como 'Disabled'.

Um usuário pode ser enganado e aceitar uma oferta de Assistência Remota não solicitada de um usuário malicioso.



<img width="999" height="791" alt="image" src="https://github.com/user-attachments/assets/486307ba-a65c-4e8f-80db-755dd48b4682" />

Certifique-se de que a opção 'Configure Solicited Remote Assistance' esteja definida como 'Disabled'.

Existe um pequeno risco de um administrador mal-intencionado obter acesso à sessão de desktop de outro usuário, no entanto, ele não pode se conectar ao computador de um usuário sem aviso prévio ou controlá-lo sem a permissão do usuário. Quando um especialista tenta se conectar, o usuário ainda pode optar por negar a conexão ou conceder ao especialista privilégios somente de visualização. O usuário deve clicar explicitamente no botão "Sim" para permitir que o especialista controle remotamente a estação de trabalho.

Computer Configuration\Policies\Administrative Templates\System\Remote Assistance\Configure Offer Remote Assistance

<img width="1003" height="783" alt="image" src="https://github.com/user-attachments/assets/84d9da72-04d4-4e49-b56f-c7bc71ea1898" />

Desabilitar estas duas configurações (somadas a todas as outras que virão) irão elevar o padrão e a maturidade de segurança do ambiente de Desktops do seu ambiente.

Na empresa que você trabalha, o recurso Remote Assistance ainda está ativo? Quais políticas vocês usam para controlar acesso remoto em endpoints?

Salve este post para usar como checklist em sua próxima auditoria de hardening.

Até o próximo artigo. 
