<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/643001fa-ca1b-4a8c-8bf5-eb5cc1abc63d" />


# Windows - Hardening Básico - Part 12 - Polêmico Bloqueio de Pendrive

Imagine o cenário, você gastou milhões em Firewall e EDR, mas o seu maior risco custa R$ 20,00 (ou menos). O pendrive perdido no estacionamento ou o brinde de evento são vetores clássicos de Initial Access que iniciam todo o efeito dominó de um incidente mais grave. Aquele pendrive que você pegou emprestado do seu filho na correria (proveniente de um notebook infestado de jogo, crack, keygen, browser extensions duvidosas e 5 versões de navegador desatualizadas) também pode ser um letal vetor de ataque.

Na estratégia de Hardening da série, o controle de dispositivos removíveis não é apenas um bloqueio chato. Este controle significa uma redução séria de superfície de ataque. Muita gente foca em vulnerabilidades complexas e esquece o básico. O Windows, por padrão, é amigável demais com dispositivos USB. Permitir que qualquer dispositivo de armazenamento seja acessado sem critério é pedir para ter um incidente de Ransomware ou exfiltração de dados.

Configure o valor da política em:

Computer Configuration > Policies > Administrative Templates > System > Removable Storage Access section 

<img width="1118" height="758" alt="image" src="https://github.com/user-attachments/assets/43b20384-bf91-4545-a354-f959ace2052b" />

Habilite esta política para negar o acesso de leitura, gravação e execução a todos os dispositivos de armazenamento removíveis (incluindo unidades USB, cartões SD e discos rígidos externos).

Esta política não bloqueia dispositivos USB que não sejam de armazenamento, como teclados, mouses ou webcams, que são classificados como dispositivos HID (Dispositivos de Interface Humana).

Na seção Acesso a Armazenamento Removível, existem várias políticas que permitem desabilitar o uso de diferentes tipos de classes de armazenamento: CDs/DVDs, disquetes, dispositivos USB, fitas, etc.

Atenção para a opção Deny execute access. Considere também esta possibilidade.

<img width="357" height="398" alt="image" src="https://github.com/user-attachments/assets/f761521d-a0e6-4f5f-a3d5-822099595677" />

Você pode implementar a política de restrição ainda mais rígidas, Escolhendo a opção "Todas as Classes de Armazenamento Removíveis: Negar Todo o Acesso" (All Removable Storage classes: Deny all access), para desabilitar completamente o acesso a todos os tipos de dispositivos de armazenamento externo. 

Este é um conjunto de configurações que provavelmente exigirá um pouco mais de mapeamento de sua parte. Se você estiver em um ambiente altamente permissivo todos os ajustes deverão ser implementados gradualmente. Este é um belo momento para fazer também o inventário físico de Hardware, que tal ? 

O que não recomendo é a criação da GPO e sua aplicação em todos os Desktops sem nenhum mapeamento dos dispositivos bem como sua funcionalidade e importância. 

Evite eventos de indisponibilidade para os usuários. Implemente gradativamente.

Salve este post como parte do seu checklist de hardening Windows.

Na empresa que você trabalha, o acesso ao Pendrive é liberado ? Ao longo da implementação de um projeto como este, você consegue imaginar todos os riscos mitigados ?
