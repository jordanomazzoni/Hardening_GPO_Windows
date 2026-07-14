<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/0a31822a-ad1f-4ae6-a04e-51f53a8386fd" />


# Windows - Hardening Básico - Part 62 - Notifications

Garanta que 'Turn off notifications network usage' esteja atribuida como 'Enabled'

Essa configuração de política impede que aplicativos usem a rede para enviar notificações de atualização de blocos, ícones de blocos, notificações pop-up ou notificações brutas. Essa configuração desativa a conexão entre o Windows e o Serviço de Notificações Push do Windows (WNS). Ela também impede que os aplicativos consultem os serviços de aplicativos para atualizar blocos.

O estado recomendado para essa configuração é: Ativado.

O Serviço de Notificações Push do Windows (WNS) é um mecanismo para receber notificações e atualizações de terceiros da nuvem/Internet. Em um ambiente de alta segurança, sistemas externos, especialmente aqueles hospedados fora da organização, devem ser impedidos de afetar as estações de trabalho seguras.

Computer Configuration\Policies\Administrative Templates\Start Menu and Taskbar\Notifications\Turn off notifications network usage

<img width="1268" height="846" alt="image" src="https://github.com/user-attachments/assets/0faeb1a9-21c1-4b5c-a6a0-ffab04d180ec" />

Garanta que 'Remove Personalized Website Recommendations from the Recommended section in the Start Menu' esteja atribuida como 'Enabled'

Esta configuração de política define se as recomendações personalizadas de sites serão exibidas no Menu Iniciar.

O estado recomendado para esta configuração é: Ativado.

As recomendações personalizadas de sites da Microsoft são baseadas em dados coletados da atividade do usuário. Esses dados podem conter informações confidenciais.

Computer Configuration\Policies\Administrative Templates\Start Menu and Taskbar\Remove Personalized Website Recommendations from the Recommended section in the Start Menu

<img width="1265" height="797" alt="image" src="https://github.com/user-attachments/assets/368b9ea0-a1d5-486e-b253-8ea2ffd670ff" />

Salve este post como parte do seu checklist de hardening Windows.
