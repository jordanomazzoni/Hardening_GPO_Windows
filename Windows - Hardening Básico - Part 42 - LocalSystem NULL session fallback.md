<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/300ab204-4d72-4042-88c7-8b46c30c3447" />


# Windows - Hardening Básico - Part 42 - LocalSystem NULL session fallback

O principal objetivo dessa configuração é impedir que um atacante que já comprometeu um serviço rodando como LocalSystem consiga atingir outros elementos da rede sem ter credenciais válidas de domínio.

Garanta que 'Network security: Allow LocalSystem NULL session fallback' esteja atribuido como 'Disabled'

Essa configuração de política determina se o NTLM pode recorrer a uma sessão NULL quando usado com o LocalSystem.

O estado recomendado para essa configuração é: Desativado.
Sessões NULL são menos seguras porque, por definição, não são autenticadas.
Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Allow LocalSystem NULL session fallback

<img width="1246" height="716" alt="image" src="https://github.com/user-attachments/assets/05e3cb98-d772-40af-b4df-8c1f84b93f0d" />

Salve este post como parte do seu checklist de hardening Windows.
