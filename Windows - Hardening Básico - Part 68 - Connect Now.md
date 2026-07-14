<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/362cea03-221b-41a1-91d9-4025dc507779" />


# Windows - Hardening Básico - Part 68 - Connect Now

Garanta que 'Configuration of wireless settings using Windows Connect Now' esteja atribuido como 'Disabled'

Essa configuração de política permite a configuração de definições de rede sem fio usando o Windows Connect Now (WCN). O Registrador WCN permite a descoberta e configuração de dispositivos via Ethernet (UPnP) em Wi-Fi 802.11 integrado, por meio da API de Dispositivos Portáteis do Windows (WPD) e via unidades flash USB. Opções adicionais estão disponíveis para permitir a descoberta e configuração em uma mídia específica.

O estado recomendado para essa configuração é: Desativado.

Essa configuração aumenta a segurança do ambiente e reduz a exposição geral ao risco relacionado à configuração de definições de rede sem fio pelo usuário. Além disso, de acordo com a Microsoft, o Windows Connect Now foi criado como uma solução para redes domésticas e pequenas empresas, e não se destina a cenários corporativos.

Computer Configuration\Policies\Administrative Templates\Network\Windows Connect Now\Configuration of wireless settings using Windows Connect Now

<img width="1264" height="842" alt="image" src="https://github.com/user-attachments/assets/6e969e0b-edda-4900-afe5-bea00f429da8" />

Garanta que 'Prohibit access of the Windows Connect Now wizards' esteja atribuido como 'Enabled'

Essa configuração de política impede o acesso aos assistentes do Windows Connect Now (WCN).

O estado recomendado para essa configuração é: Ativado.

Permitir que usuários padrão acessem o assistente do Windows Connect Now aumenta o risco e a superfície de ataque. Além disso, de acordo com a Microsoft, o Windows Connect Now foi criado como uma solução para redes domésticas e pequenas empresas, e não se destina a cenários corporativos.

Computer Configuration\Policies\Administrative Templates\Network\Windows Connect Now\Prohibit access of the Windows Connect Now wizards

<img width="1262" height="843" alt="image" src="https://github.com/user-attachments/assets/b05b1ba4-e031-4bbb-bed1-7c078b95604a" />

Salve este post como parte do seu checklist de hardening Windows.
