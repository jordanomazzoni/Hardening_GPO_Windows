<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/0ee8ecf2-e7ab-47c8-864b-ffcef53bc0cb" />


# Windows - Hardening Básico - Part 27 - Advanced Audit Policy - Account Logon - Object Access

A implementação da Advanced Audit Policy Configuration via GPO é um imperativo de governança que eleva o monitoramento de um estado passivo para rastreamento granular e de alto detalhamento, essencial para a detecção de evento para a equipe de monitoramento. 

Nos próximos passos vamos contruir a base de evidências necessária para a conformidade com frameworks globais como NIST e ISO 27001 além de trazer vida e significado aos eventos de um SOC.

1-) Garanta que a configuração 'Audit Credential Validation' esteja atribuída como 'Success and Failure'

Esta subcategoria relata os resultados de testes de validação em credenciais enviadas para uma solicitação de logon de conta de usuário. Esses eventos ocorrem no computador que tem autoridade para as credenciais. Para contas de domínio, o Controlador de Domínio é autoritativo, enquanto para contas locais, o computador local é autoritativo. Em ambientes de domínio, a maioria dos eventos de logon de conta ocorre no log de segurança dos controladores de domínio que têm autoridade para as contas de domínio. Entretanto, esses eventos podem ocorrer em outros computadores da organização quando contas locais são usadas para fazer logon. Os eventos para esta subcategoria incluem:

4774: An account was mapped for logon.

4775: An account could not be mapped for logon.

4776: The Domain Controller attempted to validate the credentials for an account.

4777: The Domain Controller failed to validate the credentials for an account.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Account Logon\Audit Credential Validation

Conteúdo do artigo
2-) Garanta que a configuração 'Audit Detailed File Share' esteja atribuída como 'Failure' 

Esta subcategoria permite auditar tentativas de acesso a arquivos e pastas em uma pasta compartilhada. Os eventos para esta subcategoria incluem:

5145: network share object was checked to see whether client can be granted desired access.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Object Access\Audit Detailed File Share

3-) Garanta que a configuração 'Audit File Share' esteja atribuída como 'Success and Failure'

Essa configuração de política permite auditar tentativas de acesso a uma pasta compartilhada.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Object Access\Audit File Share

4-) Garanta que a configuração 'Audit Other Object Access Events' esteja atribuída como 'Success and Failure' 

Essa configuração de política permite auditar eventos gerados pelo gerenciamento de trabalhos do agendador de tarefas ou objetos COM+.

Para trabalhos do agendador, são auditados os seguintes itens:

Job created.

Job deleted.

Job enabled.

Job disabled.

Job updated.

Para objetos COM+, o seguinte é auditado:

Catalog object added.

Catalog object updated.

Catalog object deleted.



Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Object Access\Audit Other Object Access Events

5-) Garanta que a configuração 'Audit Removable Storage' esteja atribuída como 'Success and Failure'

Essa configuração de política permite auditar as tentativas do usuário de acessar objetos do sistema de arquivos em um dispositivo de armazenamento removível. Um evento de auditoria de segurança é gerado apenas para todos os objetos e para todos os tipos de acesso solicitados. Se você definir essa configuração de política, um evento de auditoria será gerado sempre que uma conta acessar um objeto do sistema de arquivos em um armazenamento removível. As auditorias de sucesso registram tentativas bem-sucedidas e as auditorias de falha registram tentativas malsucedidas. Se você não definir essa configuração de política, nenhum evento de auditoria será gerado quando uma conta acessar um objeto do sistema de arquivos em um armazenamento removível.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Object Access\Audit Removable Storage

Resumo das configurações:
<img width="918" height="419" alt="image" src="https://github.com/user-attachments/assets/8be8bb9e-53f4-4478-9fb5-b98509c06192" />

<img width="1120" height="824" alt="image" src="https://github.com/user-attachments/assets/96d03425-f82d-4bb4-918c-b85fe15a0b9b" />

<img width="1116" height="841" alt="image" src="https://github.com/user-attachments/assets/8ed35fbd-baf8-4cf5-b135-b512ec41ac89" />

Salve este post como parte do seu checklist de hardening Windows.

Na empresa que você trabalha, que tal tirar o dia de hoje para conferir estas e outras configurações? Estão mesmo todas aplicadas? 
