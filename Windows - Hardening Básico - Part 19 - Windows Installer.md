<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/e00816a8-1be7-458e-bd3d-8978ae79fe94" />


# Windows - Hardening Básico - Part 19 - Windows Installer

Permitir que usuários finais detenham autonomia sobre a instalação de softwares não é apenas um risco operacional; é uma falha de governança que expande a superfície de ataque de forma desnecessária. Em uma arquitetura resiliente, o Principle of Least Privilege deve ser o alicerce que sustenta a infraestrutura, garantindo que a execução de códigos e alterações no sistema sejam restritas a agentes autorizados, mantendo o ambiente previsível e protegido contra vetores de entrada não auditados.

Garanta que a configuração 'Allow user control over installs' esteja atribuída como 'Disabled'

Garanta que a configuração 'Always install with elevated privileges' esteja atribuída como 'Disabled'

Em um ambiente corporativo gerenciado, somente a equipe de TI com direitos administrativos deve instalar ou alterar softwares em um sistema. Permitir que os usuários tenham qualquer controle sobre as instalações pode levar à instalação ou remoção de softwares não autorizados, tornando o sistema vulnerável a ataques. 

Configure o valor da política em:

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Installer\Allow user control over installs

<img width="694" height="638" alt="image" src="https://github.com/user-attachments/assets/9748a748-7cc0-432d-967a-d5d5435e623d" />

Usuários com privilégios limitados podem explorar esse recurso criando um pacote de instalação do Windows Installer que cria uma nova conta local pertencente ao grupo Administradores local integrado, adiciona sua conta atual ao grupo Administradores local integrado, instala software malicioso ou realiza outras atividades não autorizadas.

Se habilitado, usuários com conhecimento técnico podem se aproveitar das permissões concedidas por essa configuração para alterar seus privilégios e obter acesso permanente a arquivos e pastas restritos. Observe que a versão de Configuração do Usuário dessa configuração não tem garantia de segurança.

Configure o valor da política em:

 Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Installer\Always install with elevated privileges

<img width="690" height="634" alt="image" src="https://github.com/user-attachments/assets/8c5166f4-ff09-4420-8568-665a4204dd6f" />

Remover a capacidade de instalação do usuário comum não deve ser visto como uma restrição de produtividade, mas como um imperativo de resiliência cibernética. Sem esse controle, um simples acesso comprometido pode evoluir rapidamente para o controle total do sistema por agentes maliciosos.

Salve este post como parte do seu checklist de hardening Windows.

No ambiente que você gerencia hoje, a instalação de software é um processo centralizado e homologado, ou a autonomia local ainda representa um desafio para a visibilidade e resposta a incidentes do seu SOC? Como ficam os processos pertinentes ao inventário de Software com o usuário atuando de forma pulverizada? 
