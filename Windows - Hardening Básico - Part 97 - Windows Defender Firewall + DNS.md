<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/82447ccd-1860-45f0-8cf0-de4116d8dfdd" />


# Windows - Hardening Básico - Part 97 - Windows Defender Firewall + DNS



Garanta que 'Prohibit installation and configuration of Network Bridge on your DNS domain network' esteja atribuido como 'Enabled'

Você pode usar este procedimento para controlar a capacidade de um usuário instalar e configurar uma Ponte de Rede.

O estado recomendado para esta configuração é: Ativado.

A configuração Ponte de Rede, quando ativada, permite que os usuários criem uma ponte MAC (Media Access Control) de Camada 2, possibilitando a conexão de dois ou mais segmentos de rede físicos. Uma Ponte de Rede permite, portanto, que um computador conectado a duas redes diferentes compartilhe dados entre elas.

Em um ambiente corporativo gerenciado, onde há necessidade de controlar o tráfego de rede para apenas caminhos autorizados, permitir que os usuários criem uma Ponte de Rede aumenta o risco e a superfície de ataque da rede em ponte.

Para estabelecer a configuração recomendada via Política de Grupo (GP), defina o seguinte caminho da interface do usuário como Ativado:

`- Computer Configuration\Policies\Administrative Templates\Network\Network Connections\Prohibit installation and configuration of Network Bridge on your DNS domain network`

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEoWKK3bIap4w/article-inline_image-shrink_1500_2232/B4DZ4tobBbIMAU-/0/1778882032225?e=1785369600&v=beta&t=fBV9PBg1nfcNJJE5XB8D1uChjD6SQWweQCQZueZFMlQ)

Garanta que 'Prohibit use of Internet Connection Sharing on your DNS domain network' esteja atribuido como 'Enabled'

Embora essa configuração "legada" tradicionalmente se aplicasse ao uso do Compartilhamento de Conexão com a Internet (ICS) no Windows 2000, Windows XP e Server 2003, ela agora se aplica ao recurso Hotspot Móvel no Windows 10 e Server 2016.

O estado recomendado para essa configuração é: Ativado.

Aviso: Para que o Application Guard funcione corretamente, o ICS deve estar ativado. Se o Application Guard for usado no ambiente, uma exceção a esta recomendação poderá ser necessária. Para saber mais sobre como desativar partes do ICS sem afetar o Application Guard, visite: Perguntas frequentes - Microsoft Defender Application Guard | Microsoft Learn.

Observação: O Microsoft Defender Application Guard não está mais disponível a partir do Windows 11, versão 24H2. Se o ambiente estiver executando a versão 24H2 ou posterior, uma exceção a esta recomendação será necessária. Esta recomendação será removida do Benchmark em novembro de 2026, após o fim do suporte ao Windows 11 versão 23H2.

Usuários sem privilégios de administrador não devem poder ativar o recurso de Hotspot Móvel e compartilhar sua conexão com a internet com dispositivos móveis próximos.

Para configurar o recurso recomendado via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

`- Computer Configuration\Policies\Administrative Templates\Network\Network Connections\Prohibit use of Internet Connection Sharing on your DNS domain network`

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQFupDiqE16Brw/article-inline_image-shrink_1500_2232/B4DZ4toXLRJQAQ-/0/1778882016366?e=1785369600&v=beta&t=ilmB7yuvcv4gpDxDKWFCEyInTiegS-75EjpYGbRzzls)

Garanta que 'Require domain users to elevate when setting a network's location' esteja atribuido como 'Enabled'

Essa configuração de política determina se os usuários do domínio precisam de privilégios elevados para definir a localização de uma rede.

O estado recomendado para essa configuração é: Ativado.

Permitir que usuários comuns definam a localização de uma rede aumenta o risco e a superfície de ataque.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

`- Computer Configuration\Policies\Administrative Templates\Network\Network Connections\Require domain users to elevate when setting a network's location`

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQH9CWmkxnzZZg/article-inline_image-shrink_1500_2232/B4DZ4toQokJUAQ-/0/1778881989508?e=1785369600&v=beta&t=kwOj3sN8SVkyhwYMHCvIsX6gXmDviJo55DppGCB-4Lw)

Salve este post como parte do seu checklist de hardening Windows.
