<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/3d137f75-a2bb-4d38-aaf1-3e62a6cda6de" />


# Windows - Hardening Básico - Part 71 - App and Device Inventory

Garanta que 'Turn off API Sampling' esteja atribuida como 'Enabled'

Essa configuração de política determina se a amostragem de dados da API é enviada à Microsoft. A amostragem da API monitora o conjunto de APIs amostradas usadas durante a execução do sistema para ajudar a diagnosticar problemas de compatibilidade no Windows.

O estado recomendado para essa configuração é: Ativado.

Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais.

Computer Configuration\Policies\Administrative Templates\Windows Components\App and Device Inventory\Turn off API Sampling

<img width="1265" height="840" alt="image" src="https://github.com/user-attachments/assets/edecf6dd-3e4f-4465-82dc-a99f22227a9e" />

Garanta que 'Turn off Application Footprint' esteja atribuida como 'Enabled'

Essa configuração de política determina se os dados do Application Footprint são enviados para a Microsoft. O Application Footprint monitora uma amostra de atividades do registro e dos arquivos para ajudar a diagnosticar problemas de compatibilidade.

O estado recomendado para essa configuração é: Ativado.

Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais.

Computer Configuration\Policies\Administrative Templates\Windows Components\App and Device Inventory\Turn off Application Footprint

<img width="1263" height="844" alt="image" src="https://github.com/user-attachments/assets/703ae03f-c803-46d7-b4c9-93bf2e88009b" />

Garanta que 'Turn off Install Tracing' esteja atribuida como 'Enabled'

Essa configuração de política determina se os dados de Rastreamento de Instalação são enviados para a Microsoft. O Rastreamento de Instalação monitora as instalações de aplicativos para ajudar a diagnosticar problemas de compatibilidade.

O estado recomendado para essa configuração é: Ativado.

Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais.

Computer Configuration\Policies\Administrative Templates\Windows Components\App and Device Inventory\Turn off Install Tracing

<img width="1262" height="844" alt="image" src="https://github.com/user-attachments/assets/98bea811-cbca-4e60-a7bc-42256bdce6b4" />

Salve este post como parte do seu checklist de hardening Windows.
