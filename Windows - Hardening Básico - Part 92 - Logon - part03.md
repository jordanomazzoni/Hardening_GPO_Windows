<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/bfcf2213-d38f-4c63-89ae-a8a975d0b1a9" />

# Windows - Hardening Básico - Part 92 - Logon - part03

Garanta que 'Turn off picture password sign-in' esteja atribuido como 'Enabled'

Essa configuração de política permite controlar se um usuário do domínio pode fazer login usando uma senha com imagem.

O estado recomendado para essa configuração é: Ativado.

Observação: se o recurso de senha com imagem estiver permitido, a senha de domínio do usuário será armazenada em cache no cofre do sistema ao ser utilizada.

As senhas com imagem dispensam a necessidade de uma senha complexa digitada. Em um ambiente de trabalho compartilhado, uma simples observação dos gestos na tela permitiria que alguém acessasse o sistema sem precisar saber a senha complexa. Monitores verticais com uma imagem são muito mais visíveis à distância do que teclas horizontais, aumentando a probabilidade de uma observação bem-sucedida dos gestos do mouse.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Turn off picture password sign-in

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEFIN9ZftcVAg/article-inline_image-shrink_1500_2232/B4DZ4tEMx0KEAQ-/0/1778872536621?e=1785369600&v=beta&t=1HeA_SjVB8eAipkAZDU57EAEBs-koiX0LxaWX_1b6Cg)

Garanta que 'Turn on convenience PIN sign-in' esteja atribuido como 'Disabled'

Essa configuração de política permite controlar se um usuário do domínio pode entrar usando um PIN de conveniência. No Windows 10, o PIN de conveniência foi substituído pelo Passport, que possui propriedades de segurança mais robustas. Para configurar o Passport para usuários do domínio, utilize as políticas em Configuração do Computador\\Modelos Administrativos\\Componentes do Windows\\Microsoft Passport for Work.

Observação: a senha de domínio do usuário será armazenada em cache no cofre do sistema ao usar esse recurso.

Se essa configuração estiver Desativada, o Windows Hello não permitirá a configuração do reconhecimento facial ou da impressão digital do Windows Hello. Uma exceção a essa recomendação pode ser necessária se esses recursos forem usados no ambiente.

O estado recomendado para essa configuração é: Desativado.

Um PIN é criado a partir de uma seleção de caracteres muito menor do que uma senha; portanto, na maioria dos casos, um PIN será muito menos robusto do que uma senha.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Turn on convenience PIN sign-in

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEVpo5WkKVkWQ/article-inline_image-shrink_1500_2232/B4DZ4tEJdjHMAQ-/0/1778872522968?e=1785369600&v=beta&t=jq-uzVYjT-zPY5E-hzfvnUw8kBprpMj8kcwUQtmb_TM)

Salve este post como parte do seu checklist de hardening Windows.


