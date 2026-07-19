<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/e3777552-d00b-45cc-a800-5832ad5a828b" />


# Windows - Hardening Básico - Part 28 - Advanced Audit Policy - Logon/Logoff

A implementação da Advanced Audit Policy Configuration via GPO é um imperativo de governança que eleva o monitoramento de um estado passivo para rastreamento granular e de alto detalhamento, essencial para a detecção de evento para a equipe de monitoramento. 

Nos próximos passos vamos contruir a base de evidências necessária para a conformidade com frameworks globais como NIST e ISO 27001 além de trazer vida e significado aos eventos de um SOC.

1-) Garanta que a configuração 'Audit Account Lockout' esteja atribuída como 'Failure' 

Esta subcategoria registra quando a conta de um usuário é bloqueada devido a um número excessivo de tentativas de login malsucedidas. Os eventos desta subcategoria incluem:

4625: An account failed to log on.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Logon/Logoff\Audit Account Lockout

2-) Garanta que a configuração 'Audit Group Membership' esteja atribuída como 'Success' 

Esta política permite auditar as informações de associação a grupos no token de logon do usuário. Os eventos desta subcategoria são gerados no computador em que uma sessão de logon é criada. Para um logon interativo, o evento de auditoria de segurança é gerado no computador em que o usuário fez logon. Para um logon de rede, como o acesso a uma pasta compartilhada na rede, o evento de auditoria de segurança é gerado no computador que hospeda o recurso.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Logon/Logoff\Audit Group Membership

3-) Garanta que a configuração 'Audit Logoff' esteja atribuída como 'Success' 

Esta subcategoria registra quando um usuário se desconecta do sistema. Esses eventos ocorrem no computador acessado. Para logins interativos, a geração desses eventos ocorre no computador em que o usuário está conectado. Se um login de rede ocorrer para acessar um compartilhamento, esses eventos serão gerados no computador que hospeda o recurso acessado. Se você configurar essa opção como "Sem auditoria", será difícil ou impossível determinar qual usuário acessou ou tentou acessar os computadores da organização. Os eventos desta subcategoria incluem:

4634: An account was logged off.

4647: User initiated logoff.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Logon/Logoff\Audit Logoff

4-) Garanta que a configuração 'Audit Logon' esteja atribuída como 'Success and Failure'

Esta subcategoria registra quando um usuário tenta fazer login no sistema. Esses eventos ocorrem no computador acessado. Para logins interativos, a geração desses eventos ocorre no computador em que o login foi realizado. Se um login de rede ocorrer para acessar um compartilhamento, esses eventos serão gerados no computador que hospeda o recurso acessado. Se você configurar essa opção como "Sem auditoria", será difícil ou impossível determinar qual usuário acessou ou tentou acessar os computadores da organização. Os eventos desta subcategoria incluem:

4624: An account was successfully logged on.

4625: An account failed to log on.

4648: A logon was attempted using explicit credentials.

4675: SIDs were filtered.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Logon/Logoff\Audit Logon

5-) Garanta que a configuração 'Audit Other Logon/Logoff Events' esteja atribuída como 'Success and Failure' 

Esta subcategoria registra outros eventos relacionados a logon/logoff, como desconexões e reconexões de sessões dos Serviços de Área de Trabalho Remota, uso do recurso "Executar como" para executar processos em uma conta diferente e bloqueio e desbloqueio de uma estação de trabalho. Os eventos desta subcategoria incluem:

4649: A replay attack was detected.

4778: A session was reconnected to a Window Station.

4779: A session was disconnected from a Window Station.

4800: The workstation was locked.

4801: The workstation was unlocked.

4802: The screen saver was invoked.

4803: The screen saver was dismissed.

5378: The requested credentials delegation was disallowed by policy.

5632: A request was made to authenticate to a wireless network.

5633: A request was made to authenticate to a wired network.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Logon/Logoff\Audit Other Logon/Logoff Events

6-) Garanta que a configuração 'Audit Special Logon' esteja atribuída como 'Success'

Esta subcategoria registra quando um logon especial é utilizado. Um logon especial é um logon que possui privilégios equivalentes aos de administrador e pode ser usado para elevar um processo a um nível superior. Os eventos desta subcategoria incluem:

4964 : Special groups have been assigned to a new logon.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Logon/Logoff\Audit Special Logon

Resumo das configurações:
<img width="1122" height="504" alt="image" src="https://github.com/user-attachments/assets/40f55c1f-53e4-49dc-975d-ad3b90c43697" />

<img width="752" height="461" alt="image" src="https://github.com/user-attachments/assets/cd6bbadf-b987-45e6-bad3-6547dec6ba97" />

Salve este post como parte do seu checklist de hardening Windows.
