<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/4abc8fbc-c946-4cd5-af39-1c2a5c299822" />


# Windows - Hardening Básico - Part 16 - NTLMv2 session security, Require 128-bit encryption

A maturidade de um ambiente não é medida apenas pelas ferramentas de defesa que ela possui, mas pela coragem de eliminar protocolos legados e inseguros. O NTLM, embora funcional, representa uma das maiores superfícies de ataque em ambientes corporativos modernos devido à sua suscetibilidade a ataques de relay e interceptação. Reforçar os requisitos mínimos de segurança para o provedor NTLM SSP não é apenas uma configuração técnica; é um processo essencial de higiene cibernética para garantir que a autenticação interna não seja o elo mais fraco da sua corrente de proteção.

Esta configuração de política determina quais comportamentos são permitidos para clientes em aplicações que utilizam o Provedor de Suporte de Segurança NTLM (SSP). A Interface SSP (SSPI) é utilizada por aplicações que necessitam de serviços de autenticação. A configuração não modifica o funcionamento da sequência de autenticação, mas exige determinados comportamentos em aplicações que utilizam a SSPI.

Habilite ambas as opções para esta configuração de política para ajudar a proteger o tráfego de rede que utiliza o Provedor de Suporte de Segurança NTLM (NTLM SSP) contra exposição ou adulteração por um agente malicioso que tenha obtido acesso à mesma rede. Essas opções ajudam a proteger contra ataques do tipo "homem no meio" (man-in-the-middle).

As conexões NTLM falharão se o protocolo NTLMv2 e a criptografia forte (128 bits) não forem negociados simultaneamente. Aplicações cliente que impõem essas configurações não conseguirão se comunicar com servidores mais antigos que não as suportam.

Garanta que a configuração 'Network security: Minimum session security for NTLM SSP based (including secure RPC) clients' esteja atribuída como 'Require NTLMv2 session security, Require 128-bit encryption'

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Minimum session security for NTLM SSP based (including secure RPC) clients

<img width="1001" height="607" alt="image" src="https://github.com/user-attachments/assets/dbc6892e-331f-4b30-b5c0-e5c311e2db5b" />

A segurança baseada em processos nos ensina que manter protocolos legados ativos por conveniência é, na verdade, aceitar uma dívida técnica que será cobrada em um eventual incidente. Implementar o NTLMv2 com criptografia de 128 bits é um passo fundamental na higiene cibernética de qualquer organização que leva a sério a proteção de seus ativos críticos. O desafio não está apenas na configuração técnica, mas na governança necessária para mapear e modernizar o que ainda depende do passado.

Na sua infraestrutura, a compatibilidade com sistemas legados ainda dita as regras ou a segurança já assumiu o protagonismo? 
