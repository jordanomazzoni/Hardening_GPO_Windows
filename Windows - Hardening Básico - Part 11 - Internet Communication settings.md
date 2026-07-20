<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/3900bf0d-18b1-45f2-a125-688b0a9ae380" />


# Windows - Hardening Básico - Part 11 - Internet Communication settings

Drivers são a "cereja do bolo" para atacantes porque rodam com altos privilégios. Permitir que o Windows baixe drivers de impressão via HTTP é abrir uma porta para ataques de Man-in-the-Middle (MitM) ou injeção de código malicioso disfarçado de utilitário.

Os usuários podem baixar drivers que contenham código malicioso (ou enganados por campanhas de engenharia social). Os drivers de impressão não podem ser baixados via HTTP. Essa configuração de política não impede que o computador cliente imprima em impressoras na intranet ou na Internet via HTTP. Ela apenas proíbe o download de drivers que ainda não estejam instalados localmente.

Alguns recursos podem se comunicar com o fornecedor, enviando informações do sistema ou baixando dados ou componentes . Desativar essa capacidade impedirá que informações potencialmente confidenciais sejam enviadas para fora da empresa e que o sistema seja atualizado de forma imprevisível. Essa configuração impede que o computador baixe pacotes de drivers de impressão via HTTP.

Garanta que a configuração 'Turn off downloading of print drivers over HTTP' esteja atribuída como 'Enabled'

Esta configuração de política controla se o computador pode baixar pacotes de drivers de impressão via HTTP. Para configurar a impressão via HTTP, pode ser necessário baixar drivers de impressora que não estejam disponíveis na instalação padrão do sistema operacional via HTTP.

Garanta que a configuração 'Turn off Internet download for Web publishing and online ordering wizards' esteja atribuída como 'Enabled'

Em um ambiente de Segurança elevado, visibilidade é tudo. Menos tráfego misterioso saindo da sua rede (ou circulando deliberadamente entre os Desktops) significa um SOC menos sobrecarregado. Mesmo que o ganho pareça ser mínimo em um primeiro momento, eliminar esses vetores reduz o ruído e impede que o Windows tente se comunicar com serviços legados ou desnecessários.

 Configure o valor da política para:

Computer Configuration\Policies\Administrative Templates\System\Internet Communication Management\Internet Communication settings\Turn off downloading of print drivers over HTTP

Computer Configuration\Policies\Administrative Templates\System\Internet Communication Management\Internet Communication settings\Turn off Internet download for Web publishing and online ordering wizards

<img width="1122" height="747" alt="image" src="https://github.com/user-attachments/assets/9285374a-9394-48ab-b4ec-8c02bb9a4780" />

 Salve este post como parte do seu checklist de hardening Windows.

Muitos podem considerar esse tipo de configuração como excesso de zelo. Eu particularmente gosto de acreditar na direção da redução de ruído estratégico somada a uma mentalidade de Higiene de Logs.

Cada política de segurança que implementamos não é só um item de checklist. É uma barreira entre os dados sensíveis da sua empresa e um atacante que pode estar do outro lado do mundo, esperando por um erro.
