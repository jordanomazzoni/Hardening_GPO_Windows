<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/810815fc-79eb-418b-a64c-fa703dc4a22d" />


# Windows - Hardening Básico - Part 31 - (LLTDIO) driver + (RSPNDR) driver

Manter os protocolos LLTDIO (Link-Layer Topology Discovery I/O Driver) e RSPNDR (Link-Layer Topology Discovery Responder) habilitados no Windows não é um erro crítico para usuários domésticos, mas em ambientes corporativos ou redes públicas, eles representam uma superfície de ataque desnecessária.

Ambos fazem parte do protocolo LLTD, que o Windows usa para criar o Mapa de Rede (aquela representação visual de quais computadores e roteadores estão conectados entre si).

LLTDIO (Driver de E/S): Permite que o seu computador "pergunte" quem mais está na rede e onde eles estão localizados.
RSPNDR (Respondente): Permite que o seu computador "responda" a essas perguntas, tornando-se visível no mapa de rede de outros usuários.

Garanta que 'Turn on Mapper I/O (LLTDIO) driver' esteja atribuido como 'Disabled'
Essa configuração de política altera o comportamento operacional do driver de protocolo de rede Mapper I/O.

O LLTDIO permite que um computador descubra a topologia de uma rede à qual está conectado. Ele também permite que um computador inicie solicitações de Qualidade de Serviço (QoS), como estimativa de largura de banda e análise da integridade da rede.

Para ajudar a proteger contra a descoberta e conexão a dispositivos não autorizados, essa configuração deve ser desativada para impedir a resposta ao tráfego de rede para descoberta da topologia da rede.

Computer Configuration\Policies\Administrative Templates\Network\Link-Layer Topology Discovery\Turn on Mapper I/O (LLTDIO) driver

Garanta que 'Turn on Responder (RSPNDR) driver' esteja atribuido como 'Disabled'
Essa configuração de política altera o comportamento operacional do driver de protocolo de rede Responder.

O Responder permite que um computador participe de solicitações de descoberta de topologia da camada de enlace, para que possa ser descoberto e localizado na rede. Ele também permite que um computador participe de atividades de Qualidade de Serviço (QoS), como estimativa de largura de banda e análise da integridade da rede.

Para ajudar a proteger contra a descoberta e conexão com dispositivos não autorizados, essa configuração deve ser desativada para impedir a resposta ao tráfego de rede para descoberta de topologia.

Computer Configuration\Policies\Administrative Templates\Network\Link-Layer Topology Discovery\Turn on Responder (RSPNDR) driver

Confirme via Powershell: (Aplique o script como segunda camada de confirmação a depender da versão do Windows será necessário)

Disable-NetAdapterBinding -Name "*" -ComponentID ms_rspndr
Disable-NetAdapterBinding -Name "*" -ComponentID ms_lltdio

Get-NetAdapterBinding -ComponentID "ms_lltdio", "ms_rspndr" | 
    Select-Object Name, DisplayName, ComponentID, Enabled | 
    Format-Table -AutoSize
Por que manter habilitado? 
Embora do ponto de vista estrito de hardening recomendemos o desligamento, mas podem existir cenários onde mantê-los é necessário:

Diagnóstico de Rede Local facilitando a identificação visual de problemas de conectividade entre switches e endpoints.
Compatibilidade com Legado permitindo recursos de sistemas de gerenciamento antigos ou dispositivos de rede específicos utilizam o LLTD para inventário de topologia física.
Ambientes de Teste/Laboratório: a visibilidade completa da rede é mais importante que o sigilo do endpoint.

Configuração Flexível: 
(visualize nas figuras abaixo e baseado nos conceitos apresentados escolha a melhor postura para o seu ambiente).
<img width="1118" height="840" alt="image" src="https://github.com/user-attachments/assets/7fddb70c-911d-406e-9ed1-a8cee63382a3" />

<img width="1119" height="836" alt="image" src="https://github.com/user-attachments/assets/7d81fe8b-d8a9-434d-ab9e-d6f8f7028fbc" />

Salve este post como parte do seu checklist de hardening Windows.
