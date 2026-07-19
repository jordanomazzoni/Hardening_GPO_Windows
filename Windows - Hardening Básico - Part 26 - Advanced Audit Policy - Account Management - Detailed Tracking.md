<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/70d23191-ea77-47bd-867d-552799e00c42" />


# Windows - Hardening Básico - Part 26 - Advanced Audit Policy - Account Management - Detailed Tracking

A implementação da Advanced Audit Policy Configuration via GPO é um imperativo de governança que eleva o monitoramento de um estado passivo para rastreamento granular e de alto detalhamento, essencial para a detecção de evento para a equipe de monitoramento. 

Nos próximos passos vamos contruir a base de evidências necessária para a conformidade com frameworks globais como NIST e ISO 27001 além de trazer vida e significado aos eventos de um SOC.

1-) Garanta que a configuração 'Audit Application Group Management' esteja atribuída como 'Success and Failure'

Essa configuração de política permite auditar eventos gerados por alterações em grupos de aplicativos, como os seguintes:

Application group is created, changed, or deleted.

Member is added or removed from an application group.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Account Management\Audit Application Group Management

<img width="1116" height="830" alt="image" src="https://github.com/user-attachments/assets/f45fd56c-659a-4146-8a96-94ff0bdf2fd1" />

2-) Garanta que a configuração 'Audit Security Group Management' esteja atribuída como 'Success'

Esta subcategoria relata cada evento de gerenciamento de grupo de segurança, como quando um grupo de segurança é criado, alterado ou excluído ou quando um membro é adicionado ou removido de um grupo de segurança. Se você habilitar esta configuração de política de Auditoria, os administradores poderão rastrear eventos para detectar a criação maliciosa, acidental e autorizada de contas de grupos de segurança. Os eventos para esta subcategoria incluem:

4727: A security-enabled global group was created.

4728: A member was added to a security-enabled global group.

4729: A member was removed from a security-enabled global group.

4730: A security-enabled global group was deleted.

4731: A security-enabled local group was created.

4732: A member was added to a security-enabled local group.

4733: A member was removed from a security-enabled local group.

4734: A security-enabled local group was deleted.

4735: A security-enabled local group was changed.

4737: A security-enabled global group was changed.

4754: A security-enabled universal group was created.

4755: A security-enabled universal group was changed.

4756: A member was added to a security-enabled universal group.

4757: A member was removed from a security-enabled universal group.

4758: A security-enabled universal group was deleted.

4764: A group's type was changed.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Account Management\Audit Security Group Management

<img width="1116" height="814" alt="image" src="https://github.com/user-attachments/assets/2c460b8b-f79d-44c1-ae0e-65da87f86d73" />

3-) Garanta que a configuração 'Audit User Account Management' esteja atribuída como 'Success and Failure'

Esta subcategoria relata cada evento de gerenciamento de conta de usuário, como quando uma conta de usuário é criada, alterada ou excluída; uma conta de usuário foi renomeada, desabilitada ou habilitada; ou uma senha é definida ou alterada. Se você habilitar esta configuração de política de Auditoria, os administradores poderão rastrear eventos para detectar a criação maliciosa, acidental e autorizada de contas de usuário. Os eventos para esta subcategoria incluem:

4720: A user account was created.

4722: A user account was enabled.

4723: An attempt was made to change an account's password.

4724: An attempt was made to reset an account's password.

4725: A user account was disabled.

4726: A user account was deleted.

4738: A user account was changed.

4740: A user account was locked out.

4765: SID History was added to an account.

4766: An attempt to add SID History to an account failed.

4767: A user account was unlocked.

4780: The ACL was set on accounts which are members of administrators groups.

4781: The name of an account was changed:

4794: An attempt was made to set the Directory Services Restore Mode.

5376: Credential Manager credentials were backed up.

5377: Credential Manager credentials were restored from a backup.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Account Management\Audit User Account Management

<img width="1119" height="819" alt="image" src="https://github.com/user-attachments/assets/6b3996aa-ce33-49ff-9415-0106e46dc770" />



4-) Garanta que a configuração 'Audit PNP Activity' esteja atribuída como 'Success'

Essa configuração de política permite auditar quando o plug and play detecta um dispositivo externo.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Detailed Tracking\Audit PNP Activity

<img width="1123" height="835" alt="image" src="https://github.com/user-attachments/assets/e01801d0-780f-4ea6-a7d2-72fe9015f447" />

5-) Garanta que a configuração 'Audit Process Creation' esteja atribuída como 'Success'

Esta subcategoria relata a criação de um processo e o nome do programa ou usuário que o criou. Os eventos para esta subcategoria incluem:

4688: A new process has been created.

4696: A primary token was assigned to process.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Detailed Tracking\Audit Process Creation

<img width="1105" height="683" alt="image" src="https://github.com/user-attachments/assets/9c08a0c1-86be-4281-a935-b22ae9a8a81e" />

Salve este post como parte do seu checklist de hardening Windows.

Transformar esses logs em evidências auditáveis é o que separa um parque computacional passivo de uma infraestrutura tecnicamente governada e resiliente.
