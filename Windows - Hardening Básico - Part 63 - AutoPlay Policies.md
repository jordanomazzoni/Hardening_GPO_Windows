<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/927bca2a-3df5-41b5-9302-807dd7f81421" />


# Windows - Hardening Básico - Part 63 - AutoPlay Policies

Garanta que 'Disallow Autoplay for non-volume devices' esteja atribuida como 'Enabled'

Essa configuração de política desativa a Reprodução Automática para dispositivos MTP, como câmeras ou telefones.

O estado recomendado para essa configuração é: Ativado.

Um agente malicioso poderia usar esse recurso para executar um programa que danifique um computador cliente ou os dados nele contidos.

Computer Configuration\Policies\Administrative Templates\Windows Components\AutoPlay Policies\Disallow Autoplay for non-volume devices

<img width="1263" height="840" alt="image" src="https://github.com/user-attachments/assets/624193bd-d0a0-4e28-a653-1ae4fdfdb67c" />

Garanta que 'Set the default behavior for AutoRun' esteja atribuida como 'Enabled: Do not execute any autorun commands'

Essa configuração de política define o comportamento padrão para comandos de execução automática. Os comandos de execução automática geralmente são armazenados em arquivos autorun.inf. Eles costumam executar o programa de instalação ou outras rotinas.

O estado recomendado para essa configuração é: Ativado: Não executar nenhum comando de execução automática.

Antes do Windows Vista, quando uma mídia contendo um comando de execução automática era inserida, o sistema executava o programa automaticamente, sem intervenção do usuário. Isso criava uma grande preocupação de segurança, pois o código poderia ser executado sem o conhecimento do usuário. O comportamento padrão a partir do Windows Vista é perguntar ao usuário se o comando de execução automática deve ser executado. O comando de execução automática é representado como um manipulador na caixa de diálogo Reprodução Automática.

Computer Configuration\Policies\Administrative Templates\Windows Components\AutoPlay Policies\Set the default behavior for AutoRun

<img width="1263" height="842" alt="image" src="https://github.com/user-attachments/assets/d03a9fd5-06ce-44e6-8087-1f5af72d2bd6" />

Garanta que 'Turn off Autoplay' esteja atribuida como 'Enabled: All drives'

Essa configuração controla a Reprodução Automática. A Reprodução Automática inicia a leitura de uma unidade assim que a mídia é inserida, o que faz com que o arquivo de instalação de programas ou mídias de áudio seja iniciado imediatamente.

O estado recomendado para essa configuração é: Ativada: Todas as unidades.

Observação: essa configuração não pode ser usada para ativar a Reprodução Automática em unidades de computador nas quais ela está desativada por padrão, como unidades de disquete e unidades de rede.

Computer Configuration\Policies\Administrative Templates\Windows Components\AutoPlay Policies\Turn off Autoplay

<img width="1262" height="839" alt="image" src="https://github.com/user-attachments/assets/1128ac5d-ba82-47f9-9980-3d32648c7046" />

Salve este post como parte do seu checklist de hardening Windows.
