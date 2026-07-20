<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/cc4f17db-6fe2-4c97-aafd-7caba1361253" />


# Windows - Hardening Básico - Part 17 - Send NTLMv2 response only. Refuse LM & NTLM

O verdadeiro Hardening de infraestrutura não se resume a instalar camadas extras de defesa, mas em remover o que é inseguro por design. O protocolo LM e as versões iniciais do NTLM representam um elo fraco que invalida muitos outros investimentos em segurança, permitindo ataques de relay e sequestro de sessão com ferramentas simples. Ao forçar a resposta exclusiva via NTLMv2 e recusar protocolos inferiores, estamos implementando uma sanitização cibernética impactante, elevando o custo operacional para o atacante e garantindo que apenas padrões criptográficos modernos sejam aceitos no coração do Active Directory.

O estado recomendado para esta configuração é: Enviar somente resposta NTLMv2. Recusar LM e NTLM.

Os clientes usam somente autenticação NTLMv2 e usam segurança de sessão NTLMv2 se o servidor a suportar; os controladores de domínio recusam LM e NTLM (aceitam somente autenticação NTLMv2). Os clientes que não suportam autenticação NTLMv2 não poderão se autenticar no domínio e acessar recursos do domínio usando LM e NTLM.

Garanta que a configuração 'Network security: LAN Manager authentication level' esteja atribuída como 'Send NTLMv2 response only. Refuse LM & NTLM'

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: LAN Manager authentication level

<img width="1008" height="694" alt="image" src="https://github.com/user-attachments/assets/5f644183-a932-4cf7-a7b0-26a313973af4" />

O segredo de um Hardening bem-sucedido não está no clicar, mas no inventário. Antes de forçar a recusa de LM e NTLMv1, o processo exige auditoria rigorosa (Event ID 4624) para identificar aquele serviço legado ou aquela impressora antiga que ainda conversa no idioma do Windows NT. Segurança baseada em processos nos ensina que não precisamos ter medo do Hardening do ambiente, desde que tenhamos a visibilidade correta.

O Event ID 4624 nos logs de segurança do Windows indica uma tentativa de logon bem-sucedida. Quando combinado com a configuração de GPO "Enviar somente resposta NTLMv2. Recusar LM e NTLM", esse evento pode revelar comportamentos críticos de autenticação em seu ambiente.

Você já iniciou a fase de auditoria para o desligamento total do NTLMv1 ou ainda encontra resistência por conta de aplicações críticas? 
