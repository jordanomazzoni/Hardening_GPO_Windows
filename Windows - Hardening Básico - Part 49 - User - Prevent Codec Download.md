<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/3038ce96-dfb2-4fbc-bcda-f4d5caf900a9" />


# Windows - Hardening Básico - Part 49 - User - Prevent Codec Download

Garanta que 'Prevent Codec Download' esteja atribuido como 'Enabled'

Essa configuração controla se o Windows Media Player pode baixar codecs adicionais para decodificar arquivos de mídia que ele ainda não reconhece.

O estado recomendado para essa configuração é: Ativado.

Isso apresenta algum risco potencial se um arquivo de dados malicioso for aberto no Media Player e exigir a instalação de um codec adicional. Se um codec específico for necessário para uma função essencial, ele deve ser testado primeiro para garantir sua legitimidade e fornecido pelo departamento de TI da organização.

User Configuration\Policies\Administrative Templates\Windows Components\Windows Media Player\Playback\Prevent Codec Download

<img width="1262" height="842" alt="image" src="https://github.com/user-attachments/assets/b3a60908-7839-442a-b5f3-1732ca04d9f8" />

Salve este post como parte do seu checklist de hardening Windows.
