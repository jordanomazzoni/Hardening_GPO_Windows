<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/d4b93db4-9ffb-4e53-a2c0-b39e81430c1f" />


# Windows - Hardening Básico - Part 56 - Time Providers

Garanta que 'Enable Windows NTP Client' esteja atribuido como 'Enabled'

Esta configuração de política especifica se o Cliente NTP do Windows está habilitado. Habilitar o Cliente NTP do Windows permite a sincronização do relógio do computador do sistema com o(s) servidor(es) NTP.

O estado recomendado para esta configuração é: Habilitado.

Um registro de tempo confiável e preciso é importante para diversos serviços e requisitos de segurança, incluindo, entre outros, aplicativos distribuídos, serviços de autenticação, bancos de dados multiusuário e serviços de registro de logs. O uso de um cliente NTP (com operação segura) garante a precisão funcional e é um ponto crucial na análise de eventos relevantes para a segurança.

Computer Configuration\Policies\Administrative Templates\System\Windows Time Service\Time Providers\Enable Windows NTP Client

<img width="1261" height="841" alt="image" src="https://github.com/user-attachments/assets/fee1bdbc-cdbb-44ea-86a8-1677467db556" />

Garanta que 'Enable Windows NTP Server' esteja atribuido como 'Disabled'

Esta configuração de política especifica se o servidor NTP do Windows está habilitado. Desabilitar esta configuração impede que o sistema atue como um servidor NTP (fonte de tempo) para atender solicitações NTP de outros sistemas (clientes NTP).

O estado recomendado para esta configuração é: Desabilitado.

A configuração da sincronização de tempo adequada é crucial em um ambiente corporativo gerenciado, tanto pela sensibilidade dos registros de data e hora da autenticação Kerberos quanto para garantir o registro preciso de dados de segurança. Isso deve ser feito por meio de um servidor NTP conhecido. Servidores e estações de trabalho membros geralmente não devem ser fontes de tempo para outros clientes.

Computer Configuration\Policies\Administrative Templates\System\Windows Time Service\Time Providers\Enable Windows NTP Server

<img width="1263" height="838" alt="image" src="https://github.com/user-attachments/assets/29f2fdba-4507-4c5c-a63e-d0f64f51e08d" />

Garanta que 'Configure the behavior of the sudo command' esteja atribuido como 'Enabled: Disabled'

Esta configuração de política define o uso da ferramenta de linha de comando sudo.exe. O recurso sudo no Windows permite que os usuários executem comandos com privilégios elevados (como administrador) diretamente de uma sessão de console sem privilégios elevados.

O estado recomendado para esta configuração é: Ativado: Desativado.

Computer Configuration\Policies\Administrative Templates\System\Configure the behavior of the sudo command

<img width="1263" height="841" alt="image" src="https://github.com/user-attachments/assets/62223ebf-c11b-4ae1-bede-22e18ef23756" />

Salve este post como parte do seu checklist de hardening Windows.
