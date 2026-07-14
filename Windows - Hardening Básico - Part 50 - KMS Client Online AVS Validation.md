<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/358abeef-bb73-4340-a430-6df90d9eb99a" />


# Windows - Hardening Básico - Part 50 - KMS Client Online AVS Validation

Garanta que 'Turn off KMS Client Online AVS Validation' esteja atribuido como 'Enabled'

O Key Management Service (KMS) é um método de ativação de licença da Microsoft que envolve a configuração de um servidor local para armazenar as licenças de software. O próprio servidor KMS precisa se conectar à Microsoft para ativar o serviço KMS, mas os clientes subsequentes na rede podem ativar o sistema operacional Microsoft Windows e/ou seu Microsoft Office por meio do servidor KMS em vez de se conectarem diretamente à Microsoft. Essa configuração de política permite cancelar o envio automático de dados de ativação do cliente KMS para a Microsoft.

O estado recomendado para esta configuração é: Enabled .

Embora o método de licenciamento KMS não exija que os clientes KMS se conectem à Microsoft, eles ainda enviam dados de estado de ativação do cliente KMS para a Microsoft automaticamente. Em ambientes de alta segurança, os dados nunca devem ser partilhados com terceiros sem consentimento explícito, pois podem conter informações sensíveis.

Computer Configuration\Policies\Administrative Templates\Windows Components\Software Protection Platform\Turn off KMS Client Online AVS Validation

<img width="1263" height="842" alt="image" src="https://github.com/user-attachments/assets/2c5389e7-e587-43d2-9f14-3fada51c46a2" />

Salve este post como parte do seu checklist de hardening Windows.
