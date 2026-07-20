<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/bf368c72-be8c-4698-87ba-6d101efac964" />


# Windows - Hardening Básico - Part 13 - Serviços WMPNetworkSvc - upnphost - SSDPSRV - RpcLocator

Em um ambiente que busca segurança, devemos combater a presença de serviços fora de contexto e reduzir sempre que possível a superfície de software. O excesso de tráfego inútil e a comunicação desordenada entre os ativos criam uma cortina de fumaça perfeita para o adversário se esconder.

Monitorar um ambiente poluído não é apenas trabalhoso; é perigoso. Se o seu SOC está soterrado em ruído, ele está, na prática, cego e/ou atrasado na detecção de incidentes.

Garanta que a configuração 'Remote Procedure Call (RPC) Locator (RpcLocator)' esteja atribuída como 'Disabled'

Este é um serviço legado que não tem valor ou propósito além da compatibilidade de aplicativos para softwares muito antigos. Ele deve ser desativado, a menos que haja algum aplicativo antigo específico ainda em uso no sistema que o exija. Caso exista este cenário, documente, limite o tráfego, mapeie as aplicações.

Garanta que a configuração 'SSDP Discovery (SSDPSRV)' esteja atribuída como 'Disabled'

É um belo exemplo de configuração padrão de fábrica que sacrifica a segurança. 

O serviço descobre dispositivos e serviços em rede que utilizam o protocolo de Discovery SSDP, como dispositivos UPnP. Também anuncia dispositivos e serviços SSDP em execução no computador local.

Garanta que a configuração 'UPnP Device Host (upnphost)' esteja atribuída como 'Disabled'

O Universal Plug and Play (UPnP) representa um risco real de segurança, pois permite a descoberta e conexão automáticas a dispositivos de rede. Observe que o UPnP é diferente do Plug and Play (PnP) tradicional. Em um ambiente corporativo gerenciado com foco em segurança, as estações de trabalho não devem anunciar seus serviços (nem descobrir e se conectar automaticamente a serviços de rede).

Garanta que a configuração 'Windows Media Player Network Sharing Service (WMPNetworkSvc)' esteja atribuída como 'Disabled' ou 'Not Installed'

O compartilhamento de mídia em rede a partir do Media Player não tem lugar em um ambiente corporativo gerenciado. 

Atribuindo via GPO nos caminhos:

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Windows Media Player Network Sharing Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\UPnP Device Host

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\SSDP Discovery

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Remote Procedure Call (RPC) Locator


<img width="1080" height="714" alt="image" src="https://github.com/user-attachments/assets/aacc3918-672e-43db-a8f1-34818f7eef1b" />


Via PowerShell com os comandos:

Stop-Service -Name WMPNetworkSvc -Force

Set-Service -Name WMPNetworkSvc -StartupType Disabled   

Stop-Service -Name upnphost -Force

Set-Service -Name upnphost -StartupType Disabled   

Stop-Service -Name SSDPSRV -Force

Set-Service -Name SSDPSRV -StartupType Disabled   

Stop-Service -Name RpcLocator -Force

Set-Service -Name RpcLocator -StartupType Disabled 

<img width="857" height="511" alt="image" src="https://github.com/user-attachments/assets/dcb6c243-e33e-4975-9639-6644240fcec6" />

Para uma equipe de SOC, estes serviços funcionando sem justificativa significam:

Imagem padrão dos Desktops mal configurada ou sem padrão unificado (indícios de débito técnico)
Aumento de processamento, alocação de recursos e exposição das estações de trabalho (DDoS)
Protocolos e tráfego vulnerável entre Desktops facilitando eventos de reconhecimento ou captura de pacote entre dispositivos

Salve este post como parte do seu checklist de hardening Windows.

Na empresa que você trabalha, você desprende energia para construir uma imagem padrão e eliminar serviços desnecessários ? Se o SSDPSRV ou o RpcLocator voltarem à vida em um servidor já configurado, o seu monitoramento está calibrado para o alerta ? Ou o seu SIEM está sofrendo de cegueira seletiva? 
