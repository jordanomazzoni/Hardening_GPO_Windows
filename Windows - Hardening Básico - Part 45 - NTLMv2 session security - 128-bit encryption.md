<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/bcb19706-8cd0-441a-b12c-09c63d3b9957" />


# Windows - Hardening Básico - Part 45 - NTLMv2 session security - 128-bit encryption

Garanta que 'Network security: Minimum session security for NTLM SSP based (including secure RPC) servers' esteja atribuido como 'Require NTLMv2 session security, Require 128-bit encryption'

Essa configuração de política determina quais comportamentos são permitidos pelos servidores para aplicativos que usam o NTLM Security Support Provider (SSP). A Interface SSP (SSPI) é usada por aplicativos que precisam de serviços de autenticação. A configuração não modifica o funcionamento da sequência de autenticação, mas exige determinados comportamentos em aplicativos que usam o SSPI.

O estado recomendado para esta configuração é: Exigir segurança de sessão NTLMv2, Exigir criptografia de 128 bits.

Habilite todas as opções para esta configuração de política para ajudar a proteger o tráfego de rede que usa o NTLM Security Support Provider (NTLM SSP) contra exposição ou adulteração por um agente de ameaça que obteve acesso à mesma rede. Essas opções ajudam a proteger contra ataques man-in-the-middle.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Minimum session security for NTLM SSP based (including secure RPC) servers

<img width="1259" height="736" alt="image" src="https://github.com/user-attachments/assets/d19f5dff-b021-4e02-843d-66ac9979e9aa" />

As conexões NTLM falharão se o protocolo NTLMv2 e a criptografia forte (128 bits) não forem negociados. Os aplicativos de servidor que impõem essas configurações não conseguirão se comunicar com servidores mais antigos que não as suportam.

Salve este post como parte do seu checklist de hardening Windows.
