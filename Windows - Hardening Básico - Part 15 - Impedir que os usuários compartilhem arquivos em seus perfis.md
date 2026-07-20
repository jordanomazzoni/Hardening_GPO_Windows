<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f2973722-4c52-4c74-a2dc-3be9ba4d9ada" />


# Windows - Hardening Básico - Part 15 - Impedir que os usuários compartilhem arquivos em seus perfis

O Hardening de infraestrutura exige a desativação de qualquer funcionalidade que amplie desnecessariamente a superfície de ataque sem um propósito claro de negócio. Permitir que o compartilhamento de arquivos ocorra a nível de perfil de usuário introduz riscos críticos de movimentação lateral e vazamento inadvertido de dados. O controle rigoroso dessa política é essencial para garantir que a higiene cibernética da rede não seja comprometida por ações isoladas de usuários finais.

Essa configuração de política determina se os usuários podem compartilhar arquivos dentro de seus perfis. Por padrão, os usuários podem compartilhar arquivos de seus perfis com outros usuários na rede após um administrador autorizar o compartilhamento do computador. Um administrador pode autorizar o compartilhamento do computador usando o assistente de compartilhamento para compartilhar um arquivo dentro do perfil.

Se não estiver configurado corretamente, um usuário pode compartilhar acidentalmente dados confidenciais com usuários não autorizados. Em um ambiente corporativo gerenciado, a empresa deve fornecer um local gerenciado para o compartilhamento de arquivos, como um servidor de arquivos ou o SharePoint, em vez de permitir que o usuário compartilhe arquivos diretamente de seu próprio perfil.

Garanta que a configuração 'Prevent users from sharing files within their profile.' esteja atribuída como 'Enabled'

Configure o valor da política em:

User Configuration\Policies\Administrative Templates\Windows Components\Network Sharing\Prevent users from sharing files within their profile.

<img width="1119" height="839" alt="image" src="https://github.com/user-attachments/assets/fba8053e-ef93-43f2-8599-7b6709152d0c" />

A segurança baseada em processos exige que a configuração de ativos siga um padrão de Hardening rigoroso. Nesse cenário, qual é a maturidade da gestão de privilégios administrativos para usuários comuns? Permitir autonomia de configuração sem governança é criar uma vulnerabilidade por design. 

Paralelamente, a comunicação direta entre desktops é um dos principais vetores para a propagação de ransomware. Você considera o bloqueio desse tráfego como parte da higiene cibernética da sua infraestrutura?
