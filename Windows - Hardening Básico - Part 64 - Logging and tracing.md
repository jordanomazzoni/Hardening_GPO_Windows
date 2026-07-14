<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/084dd8e2-f354-456f-9a9e-c66c8c39aeca" />


# Windows - Hardening Básico - Part 64 - Logging and tracing

Garanta que 'Configure security policy processing: Do not apply during periodic background processing' esteja atribuido como 'Enabled: FALSE'

A opção "Não aplicar durante o processamento periódico em segundo plano" impede que o sistema atualize as políticas de segurança afetadas em segundo plano enquanto o computador está em uso. Quando as atualizações em segundo plano estão desativadas, as atualizações das políticas de segurança não entrarão em vigor até o próximo logon do usuário ou reinicialização do sistema.

Essa configuração afeta todas as configurações de política que usam o modelo de segurança integrado da Política de Grupo (por exemplo, Configurações do Windows\Configurações de Segurança).

O estado recomendado para essa configuração é: Ativado: FALSO (desmarcado).

Definir essa opção como falsa (desmarcada) garantirá que as alterações na política de segurança do domínio sejam aplicadas mais rapidamente, em comparação com a espera até o próximo logon do usuário ou reinicialização do sistema.

Computer Configuration\Policies\Administrative Templates\System\Group Policy\Configure security policy processing

<img width="1265" height="814" alt="image" src="https://github.com/user-attachments/assets/7d7f403c-cad0-46ec-a127-d0755bbd0558" />

Garanta que 'Configure security policy processing: Process even if the Group Policy objects have not changed' esteja atribuido como 'Enabled: TRUE'

A opção "Processar mesmo que os objetos de Política de Grupo não tenham sido alterados" atualiza e reaplica as políticas de segurança mesmo que elas não tenham sido alteradas.

Essa configuração afeta todas as configurações de política dentro do modelo de segurança integrado da Política de Grupo (por exemplo, Configurações do Windows\Configurações de Segurança).

O estado recomendado para essa configuração é: Ativado: VERDADEIRO (marcado).

Definir essa opção como verdadeira (marcada) garantirá que as alterações locais não autorizadas sejam revertidas para corresponder às configurações da Política de Grupo baseada em domínio.

Computer Configuration\Policies\Administrative Templates\System\Group Policy\Configure security policy processing

<img width="1265" height="814" alt="image" src="https://github.com/user-attachments/assets/75bec2d6-050b-431c-b03e-59f29c4d9dd4" />

Garanta que 'Continue experiences on this device' esteja atribuido como 'Disabled'

Essa configuração de política determina se o dispositivo Windows tem permissão para participar de experiências entre dispositivos (continuar experiências).

O estado recomendado para essa configuração é: Desativado.

Uma experiência entre dispositivos ocorre quando um sistema pode acessar um aplicativo e enviar mensagens para outros dispositivos. Em um ambiente corporativo gerenciado, somente sistemas confiáveis devem se comunicar na rede. O acesso a qualquer outro sistema deve ser proibido.

Computer Configuration\Policies\Administrative Templates\System\Group Policy\Continue experiences on this device

<img width="1262" height="842" alt="image" src="https://github.com/user-attachments/assets/39ecb3bb-5ded-46c9-b12e-00d4ff2fee7d" />

Salve este post como parte do seu checklist de hardening Windows.
