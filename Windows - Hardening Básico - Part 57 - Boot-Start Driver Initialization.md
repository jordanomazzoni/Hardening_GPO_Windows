<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/5fd7f26c-f542-4b60-8621-419846b4f370" />


# Windows - Hardening Básico - Part 57 - Boot-Start Driver Initialization

Garanta que 'Boot-Start Driver Initialization Policy' esteja atribuido como 'Enabled: Good, unknown and bad but critical'

Esta configuração de política permite especificar quais drivers de inicialização serão carregados com base em uma classificação determinada pelo driver de inicialização do Early Launch Antimalware. O driver de inicialização do Early Launch Antimalware pode retornar as seguintes classificações para cada driver de inicialização:

Bom: O driver foi assinado e não foi adulterado.
Ruim: O driver foi identificado como malware. Recomenda-se não permitir a inicialização de drivers sabidamente maliciosos.
Ruim, mas necessário para inicialização: O driver foi identificado como malware, mas o computador não pode inicializar corretamente sem carregá-lo.
Desconhecido: Este driver não foi atestado pelo seu aplicativo de detecção de malware e não foi classificado pelo driver de inicialização do Early Launch Antimalware.

Ao habilitar esta configuração de política, você poderá escolher quais drivers de inicialização serão carregados na próxima vez que o computador for iniciado.

Se o seu aplicativo de detecção de malware não incluir um driver de inicialização do Early Launch Antimalware ou se o driver de inicialização do Early Launch Antimalware estiver desativado, esta configuração não terá efeito e todos os drivers de inicialização serão inicializados.

O estado recomendado para esta configuração é: Ativado: Bom, desconhecido e ruim, mas crítico.

Computer Configuration\Policies\Administrative Templates\System\Early Launch Antimalware\Boot-Start Driver Initialization Policy

<img width="1261" height="841" alt="image" src="https://github.com/user-attachments/assets/9fdb7895-bbfa-474b-a729-ecc3ca72f868" />

Salve este post como parte do seu checklist de hardening Windows.
