![](https://media.licdn.com/dms/image/v2/D4D12AQFH5sh6cWsplg/article-cover_image-shrink_720_1280/B4DZ4tgrc7HAAQ-/0/1778880004174?e=1785369600&v=beta&t=SiBJpFSyep4_aqcmC74ZkEuDB3YiiODCBHGrk6jLTv0)

# Windows - Hardening Básico - Part 94 - Automatic Updates - End user experience


Garanta que 'Configure Automatic Updates' esteja atribuido como 'Enabled'

Esta configuração de política especifica se os computadores em seu ambiente receberão atualizações de segurança do Windows Update ou do WSUS. Se você configurar esta política como Ativada, o sistema operacional reconhecerá quando uma conexão de rede estiver disponível e a utilizará para pesquisar no Windows Update ou no site da intranet designado as atualizações aplicáveis.

Após configurar esta política como Ativada, selecione uma das quatro opções a seguir na caixa de diálogo Configurar Propriedades de Atualizações Automáticas para especificar como o serviço funcionará:

2 - Notificar para download e instalação automática (Notificar antes de baixar qualquer atualização)

3 - Download automático e notificação para instalação (Baixar as atualizações automaticamente e notificar quando estiverem prontas para instalação.) (Configuração padrão)

4 - Download automático e agendamento de instalação (Baixar automaticamente as atualizações e instalá-las de acordo com o agendamento especificado abaixo.)

5 - Permitir que o administrador local escolha a configuração (Deixar a decisão sobre as opções acima a cargo dos administradores locais (Não recomendado))

O estado recomendado para esta configuração é: Ativada.

Embora cada versão do Windows seja exaustivamente testada antes do lançamento, é possível que problemas sejam descobertos após a distribuição dos produtos. A configuração "Configurar atualizações automáticas" pode ajudar a garantir que os computadores em seu ambiente sempre tenham as atualizações críticas mais recentes do sistema operacional e os pacotes de serviços instalados.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como "Habilitado":

* Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Update\\Manage end user experience\\Configure Automatic Updates

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEwibAKgZN0Dg/article-inline_image-shrink_1000_1488/B4DZ4tgxA5G4AI-/0/1778880025094?e=1785369600&v=beta&t=X5ZuGg6qNwmgPZzb6fiJrQTM_9e1jMtXREngcuQ3jLI)

Garanta que 'Configure Automatic Updates: Scheduled install day' esteja atribuido como '0 - Every day'

Esta configuração de política especifica quando os computadores em seu ambiente receberão atualizações de segurança do Windows Update ou do WSUS.

O estado recomendado para esta configuração é: 0 - Diariamente.

Observação: esta configuração só se aplica se a opção 4 - Baixar automaticamente e agendar a instalação estiver selecionada na recomendação "Configurar atualizações automáticas". Ela não terá efeito se qualquer outra opção for selecionada.

Embora cada versão do Windows seja rigorosamente testada antes do lançamento, é possível que problemas sejam descobertos após a distribuição dos produtos. A configuração "Configurar atualizações automáticas" pode ajudar a garantir que os computadores em seu ambiente sempre tenham as atualizações críticas do sistema operacional e os service packs mais recentes instalados.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como 0 - Diariamente:

* Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Update\\Manage end user experience\\Configure Automatic Updates: Scheduled install day

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEdLtWF7u9Pvg/article-inline_image-shrink_1500_2232/B4DZ4tg1ESIMAU-/0/1778880041659?e=1785369600&v=beta&t=fHUXyvHsChoz2sKielIfP-ZJGMaOadqFnaE7VMz98sM)

Garanta que 'Enable features introduced via servicing that are off by default' esteja atribuido como 'Disabled'

Esta configuração de política define se os recursos e melhorias introduzidos por meio de atualizações cumulativas mensais (manutenção) serão habilitados no sistema.

O estado recomendado para esta configuração é: Desabilitado.

Frequentemente, novos recursos ou melhorias habilitados por padrão (antes que os administradores de TI estejam preparados para gerenciá-los) podem impactar negativamente a experiência do usuário ou introduzir bugs e riscos de segurança.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desabilitado:

* Computer Configuration\\Policies\\Administrative Templates\\\\Windows Components\\Windows Update\\Manage end user experience\\Enable features introduced via servicing that are off by default

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQHI2WoDeWudfw/article-inline_image-shrink_1500_2232/B4DZ4tg5TlJUAQ-/0/1778880058993?e=1785369600&v=beta&t=iFsDSvCaMuRWGCCWdwYsJTDEpoawhwgfp68ZXfWec_s)

Garanta que 'Remove access to “Pause updates” feature' esteja atribuido como 'Enabled'

Esta política remove o acesso ao recurso "Pausar atualizações".

O estado recomendado para esta configuração é: Ativado.

Para garantir que as atualizações de segurança e do sistema sejam aplicadas, os administradores de sistema devem controlar quando as atualizações são aplicadas aos sistemas.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

* Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Update\\Manage end user experience\\Remove access to “Pause updates” feature

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQHdRYVOjnzL0A/article-inline_image-shrink_1000_1488/B4DZ4tg_M2HoAM-/0/1778880083084?e=1785369600&v=beta&t=_iXfZacqKGthgBZPDa-PnRl9mk5QgZRGRwjWivFiWik)

Salve este post como parte do seu checklist de hardening Windows.
