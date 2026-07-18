<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f8e37f33-9eac-4e3f-b364-928a3509fe0f" />


# Windows - Hardening Básico - Part 38 - SAM change password RPC methods policy

Garanta que 'Configure SAM change password RPC methods policy esteja atribuido como 'Enabled: Block all change password RPC methods'

Essa configuração de política determina quais métodos RPC podem ser usados para alterar senhas armazenadas no Gerenciador de Contas de Segurança (SAM).

O estado recomendado para essa configuração é: Ativado: Bloquear todos os métodos RPC de alteração de senha.

As senhas de usuário armazenadas no SAM devem ser alteradas somente a partir de um Controlador de Domínio usando métodos seguros.

Computer Configuration\Policies\Administrative Templates\System\Security Account Manager\Configure SAM change password RPC methods policy

<img width="1262" height="843" alt="image" src="https://github.com/user-attachments/assets/b3872a20-6336-4917-bcfc-1c5b37b68511" />

Salve este post como parte do seu checklist de hardening Windows.
