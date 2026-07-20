<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/7bffeea5-408d-478a-89db-43bfd9fc2b95" />


# Windows - Hardening Básico - Part 10 - Digitally sign communications (always)

Você já parou para pensar que um simples pacote SMB não assinado pode ser a brecha que derruba toda a sua rede? 

A política 'Digitally sign communications (always)' é essencial para mitigar ataques de man-in-the-middle em redes corporativas. Se esta política estiver habilitada, o cliente SMB só se comunicará com um servidor SMB que realize a assinatura de pacotes SMB.

Garanta que a configuração 'Microsoft network client: Digitally sign communications (always)' esteja atribuída como 'Enabled'

Garanta que a configuração 'Microsoft network server: Digitally sign communications (always)' esteja atribuída como 'Enabled'

Esta configuração de política determina se a assinatura de pacotes é obrigatória para o componente cliente SMB (Server Message Block). O SMB é o protocolo de compartilhamento de recursos suportado por muitos sistemas operacionais Windows. Ele é a base do NetBIOS e de muitos outros protocolos. As assinaturas SMB autenticam tanto os usuários quanto os servidores que hospedam os dados. Se qualquer uma das partes falhar no processo de autenticação, a transmissão de dados não ocorrerá.

O sequestro de sessão utiliza ferramentas que permitem que agentes maliciosos com acesso à mesma rede que o cliente ou servidor interrompam, encerrem ou roubem uma sessão em andamento. Esses agentes podem interceptar e modificar pacotes SMB não assinados e, em seguida, modificar o tráfego e encaminhá-lo para que o servidor execute ações indesejáveis. Alternativamente, os agentes maliciosos podem se passar pelo servidor ou cliente após autenticação legítima e obter acesso não autorizado aos dados.

O cliente de rede Microsoft não se comunicará com um servidor de rede Microsoft a menos que este concorde em realizar a assinatura de pacotes SMB.

A implementação da assinatura SMB pode afetar negativamente o desempenho, pois cada pacote precisa ser assinado e verificado. Se essas configurações estiverem habilitadas em um servidor que desempenha múltiplas funções, como um servidor de pequenas empresas que atua como Controlador de Domínio, servidor de arquivos, servidor de impressão e servidor de aplicativos, o desempenho pode ser significativamente reduzido. Além disso, se os computadores estiverem configurados para ignorar todas as comunicações SMB não assinadas, aplicativos e sistemas operacionais mais antigos não poderão se conectar. No entanto, se a assinatura SMB for completamente desativada, os computadores ficarão vulneráveis a ataques de sequestro de sessão. Entenda os riscos e teste antes de implementar.

Configure o valor da política para:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Microsoft network client: Digitally sign communications (always)

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Microsoft network server: Digitally sign communications (always)

<img width="1116" height="844" alt="image" src="https://github.com/user-attachments/assets/07ed3547-a63d-4e6a-8bfd-b384615a6d99" />

Cada política de segurança que implementamos não é só um item de checklist. É uma barreira entre os dados sensíveis da sua empresa e um atacante que pode estar do outro lado do mundo, esperando por um erro.

Comando Powershell para verificação:

Get-SmbClientConfiguration | Select EnableSecuritySignature, RequireSecuritySignature 
Salve este post como parte do seu checklist de hardening Windows.

Na empresa que você trabalha, esta configuração está habilitada ? Como você mitiga, monitora ou realiza a detecção de ataques de man-in-the-middle ?
