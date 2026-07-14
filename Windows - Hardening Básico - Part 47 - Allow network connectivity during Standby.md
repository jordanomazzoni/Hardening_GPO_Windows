<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/a4df60ab-18de-4a0d-9105-332e2ef36ea0" />


# Windows - Hardening Básico - Part 47 - Allow network connectivity during Standby

Garanta que 'Allow network connectivity during connected-standby (on battery)' esteja atribuido como 'Disabled' 

Essa configuração de política permite controlar o estado da conectividade de rede em modo de espera em sistemas modernos com capacidade para esse recurso. Desativar essa configuração garante que o computador não ficará acessível a agentes maliciosos por meio de uma rede WLAN enquanto estiver sem supervisão, funcionando com bateria ou em estado de suspensão.

Computer Configuration\Policies\Administrative Templates\System\Power Management\Sleep Settings\Allow network connectivity during connected-standby (on battery)

Garanta que 'Allow network connectivity during connected-standby (plugged in)' esteja atribuido como 'Disabled' 

Essa configuração de política permite controlar o estado da conectividade de rede em modo de espera em sistemas modernos com capacidade para esse recurso. Desativar essa configuração garante que o computador não ficará acessível a agentes maliciosos por meio de uma rede WLAN enquanto estiver sem supervisão, conectado à tomada e em estado de suspensão.

Computer Configuration\Policies\Administrative Templates\System\Power Management\Sleep Settings\Allow network connectivity during connected-standby (plugged in)

Garanta que 'Require a password when a computer wakes (on battery)' esteja atribuido como 'Enabled' 

Especifica se o usuário será solicitado a inserir uma senha quando o sistema for retomado do modo de suspensão. Habilitar essa configuração garante que qualquer pessoa que ativar um computador desacompanhado do modo de suspensão precisará fornecer as credenciais de login antes de acessar o sistema.

Computer Configuration\Policies\Administrative Templates\System\Power Management\Sleep Settings\Require a password when a computer wakes (on battery)

Garanta que 'Require a password when a computer wakes (plugged in)' esteja atribuido como 'Enabled'

Especifica se o usuário será solicitado a inserir uma senha quando o sistema for retomado do modo de suspensão. Habilitar essa configuração garante que qualquer pessoa que ativar um computador desacompanhado do modo de suspensão precisará fornecer as credenciais de login antes de acessar o sistema.

Computer Configuration\Policies\Administrative Templates\System\Power Management\Sleep Settings\Require a password when a computer wakes (plugged in)

Resumo das configurações:
<img width="1265" height="842" alt="image" src="https://github.com/user-attachments/assets/aa5a2c56-ffc7-4087-a996-b1013b1e0a39" />

<img width="1263" height="842" alt="image" src="https://github.com/user-attachments/assets/0cc9f65a-d71d-42f6-b623-b7dbdd6829a8" />

Salve este post como parte do seu checklist de hardening Windows.
