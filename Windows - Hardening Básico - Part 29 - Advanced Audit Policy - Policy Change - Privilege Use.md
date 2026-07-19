<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/9b8dab61-06ed-45e4-a8b3-1447f2069a2c" />


# Windows - Hardening Básico - Part 29 - Advanced Audit Policy - Policy Change - Privilege Use

A implementação da Advanced Audit Policy Configuration via GPO é um imperativo de governança que eleva o monitoramento de um estado passivo para rastreamento granular e de alto detalhamento, essencial para a detecção de evento para a equipe de monitoramento. 

Nos próximos passos vamos contruir a base de evidências necessária para a conformidade com frameworks globais como NIST e ISO 27001 além de trazer vida e significado aos eventos de um SOC.

1-) Garanta que a configuração 'Audit Audit Policy Change' esteja atribuída como 'Success'

Esta subcategoria relata alterações na política de auditoria, incluindo alterações de SACL. 

Os eventos para esta subcategoria incluem:

4715: The audit policy (SACL) on an object was changed.

4719: System audit policy was changed.

4902: The Per-user audit policy table was created.

4904: An attempt was made to register a security event source.

4905: An attempt was made to unregister a security event source.

4906: The CrashOnAuditFail value has changed.

4907: Auditing settings on object were changed.

4908: Special Groups Logon table modified.

4912: Per User Audit Policy was changed.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Policy Change\Audit Audit Policy Change

2-) Garanta que a configuração 'Audit Authentication Policy Change' esteja atribuída como 'Success'

Esta subcategoria relata alterações na política de autenticação. Os eventos para esta subcategoria incluem:

4706: A new trust was created to a domain.

4707: A trust to a domain was removed.

4713: Kerberos policy was changed.

4716: Trusted domain information was modified.

4717: System security access was granted to an account.

4718: System security access was removed from an account.

4739: Domain Policy was changed.

4864: A namespace collision was detected.

4865: A trusted forest information entry was added.

4866: A trusted forest information entry was removed.

4867: A trusted forest information entry was modified.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Policy Change\Audit Authentication Policy Change

3-) Garanta que a configuração 'Audit Authorization Policy Change' esteja atribuída como 'Success'

Esta subcategoria relata alterações na política de autorização. Os eventos para esta subcategoria incluem:

4703: A user right was adjusted.

4704: A user right was assigned.

4705: A user right was removed.

4670: Permissions on an object were changed.

4911: Resource attributes of the object were changed.

4913: Central Access Policy on the object was changed.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Policy Change\Audit Authorization Policy Change

4-) Garanta que a configuração 'Audit MPSSVC Rule-Level Policy Change' esteja atribuída como 'Success and Failure' 

Esta subcategoria determina se o sistema operacional gera eventos de auditoria quando são feitas alterações nas regras de política do Serviço de Proteção Microsoft (MPSSVC.exe). Os eventos para esta subcategoria incluem:

4944: The following policy was active when the Windows Firewall started.

4945: A rule was listed when the Windows Firewall started.

4946: A change has been made to Windows Firewall exception list. A rule was added.

4947: A change has been made to Windows Firewall exception list. A rule was modified.

4948: A change has been made to Windows Firewall exception list. A rule was deleted.

4949: Windows Firewall settings were restored to the default values.

4950: A Windows Firewall setting has changed.

4951: A rule has been ignored because its major version number was not recognized by Windows Firewall.

4952: Parts of a rule have been ignored because its minor version number was not recognized by Windows Firewall. The other parts of the rule will be enforced.

4953: A rule has been ignored by Windows Firewall because it could not parse the rule.

4954: Windows Firewall Group Policy settings have changed. The new settings have been applied.

4956: Windows Firewall has changed the active profile.

4957: Windows Firewall did not apply the following rule.

4958: Windows Firewall did not apply the following rule because the rule referred to items not configured on this computer.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Policy Change\Audit MPSSVC Rule-Level Policy Change

5-) Garanta que a configuração 'Audit Other Policy Change Events' esteja atribuída como 'Failure'

Esta subcategoria contém eventos sobre alterações na política do Agente de Recuperação de Dados EFS, alterações no filtro da Plataforma de Filtragem do Windows, status nas atualizações das configurações da política de segurança para configurações locais da Política de Grupo, alterações na Política de Acesso Central e eventos detalhados de solução de problemas para operações criptográficas de próxima geração (CNG).

5063: A cryptographic provider operation was attempted.

5064: A cryptographic context operation was attempted.

5065: A cryptographic context modification was attempted.

5066: A cryptographic function operation was attempted.

5067: A cryptographic function modification was attempted.

5068: A cryptographic function provider operation was attempted.

5069: A cryptographic function property operation was attempted.

5070: A cryptographic function property modification was attempted.

6145: One or more errors occurred while processing security policy in the group policy objects.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Policy Change\Audit Other Policy Change Events

6-) Garanta que a configuração 'Audit Sensitive Privilege Use' esteja atribuída como 'Success'

Esta subcategoria informa quando uma conta de usuário ou serviço usa um privilégio confidencial. Um privilégio confidencial inclui os seguintes direitos de usuário:

Act as part of the operating system

Back up files and directories

Create a token object

Debug programs

Enable computer and user accounts to be trusted for delegation

Generate security audits

Impersonate a client after authentication

Load and unload device drivers

Manage auditing and security log

Modify firmware environment values

Replace a process-level token

Restore files and directories

Take ownership of files or other objects

Auditing this subcategory will create a high volume of events. Events for this subcategory include:

4672: Special privileges assigned to new logon.

4673: A privileged service was called.

4674: An operation was attempted on a privileged object.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Privilege Use\Audit Sensitive Privilege Use



Resumo das configurações:
<img width="1116" height="846" alt="image" src="https://github.com/user-attachments/assets/b97b737d-728a-4fed-ab66-12850af34ff0" />

<img width="1118" height="827" alt="image" src="https://github.com/user-attachments/assets/30eefda6-41f4-4dc1-8a91-29e255803c37" />

<img width="483" height="162" alt="image" src="https://github.com/user-attachments/assets/5c840935-0b44-47b1-8d23-b41c68bec5a5" />

Salve este post como parte do seu checklist de hardening Windows.
