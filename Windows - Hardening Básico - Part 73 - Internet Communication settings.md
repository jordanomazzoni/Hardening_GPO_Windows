<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f251cd68-f8bb-4991-8cbc-d0b5d7407a70" />


# Windows - Hardening Básico - Part 73 - Internet Communication settings

Garanta que 'Turn off access to the Store' esteja atribuido como 'Enabled'

Essa configuração de política especifica se o serviço da Loja deve ser usado para encontrar um aplicativo para abrir um arquivo com um tipo de arquivo ou protocolo não reconhecido. Quando um usuário abre um arquivo ou usa um protocolo que não está associado a nenhum aplicativo no computador, ele tem a opção de selecionar um aplicativo local ou usar o serviço da Loja para encontrar um aplicativo.

O estado recomendado para essa configuração é: Ativado.

O serviço da Loja é um ponto de venda integrado ao Windows, voltado principalmente para o usuário final. Em um ambiente corporativo gerenciado, o departamento de TI deve gerenciar a instalação de todos os aplicativos para reduzir o risco de instalação de software vulnerável.

Computer Configuration\Policies\Administrative Templates\System\Internet Communication Management\Internet Communication settings\Turn off access to the Store

<img width="1265" height="848" alt="image" src="https://github.com/user-attachments/assets/97e94d7f-97e3-4498-b79a-f52ffc595799" />

Garanta que 'Turn off downloading of print drivers over HTTP' esteja atribuido como 'Enabled'

Essa configuração de política controla se o computador pode baixar pacotes de drivers de impressão via HTTP. Para configurar a impressão via HTTP, pode ser necessário baixar drivers de impressora que não estejam disponíveis na instalação padrão do sistema operacional via HTTP.

O estado recomendado para essa configuração é: Ativado.

Os usuários podem baixar drivers que contenham código malicioso.

Computer Configuration\Policies\Administrative Templates\System\Internet Communication Management\Internet Communication settings\Turn off downloading of print drivers over HTTP

<img width="1265" height="816" alt="image" src="https://github.com/user-attachments/assets/7be2711c-0fa8-429d-ada3-9e20a3483495" />

Garanta que 'Turn off Internet Connection Wizard if URL connection is referring to Microsoft . com' esteja atribuido como 'Enabled'

Essa configuração de política especifica se o Assistente de Conexão com a Internet pode se conectar à Microsoft para baixar uma lista de provedores de serviços de Internet (ISPs).

O estado recomendado para essa configuração é: Ativado.

Em um ambiente corporativo gerenciado, queremos reduzir o risco de um usuário expor dados confidenciais sem saber.

Computer Configuration\Policies\Administrative Templates\System\Internet Communication Management\Internet Communication settings\Turn off Internet Connection Wizard if URL connection is referring to Microsoft . com

<img width="1264" height="817" alt="image" src="https://github.com/user-attachments/assets/567a0776-128f-4544-9a6f-72d59c884288" />

Resumo das configurações:
<img width="1265" height="552" alt="image" src="https://github.com/user-attachments/assets/b85e3de4-d0f6-4aef-aa87-1149a9223d43" />

Garanta que 'Turn off Internet Connection Wizard if URL connection is referring to Microsoft . com' is set to 'Enabled' 

Garanta que 'Turn off Internet download for Web publishing and online ordering wizards' is set to 'Enabled' 

Garanta que 'Turn off printing over HTTP' esteja atribuido como 'Enabled' 

Garanta que 'Turn off Registration if URL connection is referring to Microsoft . com' esteja atribuido como 'Enabled' 

Garanta que 'Turn off Search Companion content file updates' esteja atribuido como 'Enabled' 

Garanta que 'Turn off the "Order Prints" picture task' esteja atribuido como 'Enabled' 

Garanta que 'Turn off the "Publish to Web" task for files and folders' esteja atribuido como 'Enabled' 

Garanta que 'Turn off the Windows Messenger Customer Experience Improvement Program' esteja atribuido como 'Enabled' 

Garanta que 'Turn off Windows Customer Experience Improvement Program' esteja atribuido como 'Enabled' 

Garanta que 'Turn off Windows Error Reporting' esteja atribuido como 'Enabled'

Salve este post como parte do seu checklist de hardening Windows.
