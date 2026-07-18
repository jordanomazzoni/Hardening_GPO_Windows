<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/94be984b-c56c-4ecd-ab92-54d9470df730" />


# Windows - Hardening Básico - Part 34 - RPC over TCP port - PC packet level privacy

A proteção do Spooler de Impressão vai muito além de apenas "desativar o serviço". A verdadeira resiliência reside em como as comunicações internas e externas são autenticadas e transportadas. Vulnerabilidades como a CVE-2021-1678 demonstraram que falhas na associação RPC (Remote Procedure Call) permitem ataques de spoofing e bypass de segurança, transformando o tráfego de impressão em um vetor de comprometimento de credenciais. Fortalecer os requisitos de privacidade em nível de pacote e evitar o uso de portas estáticas previsíveis são passos fundamentais para reduzir a previsibilidade do sistema e elevar o custo de ataque para o adversário (atrasando-o).

Garanta que 'Configure RPC over TCP port' esteja atribuido como 'Enabled: 0'

Essa configuração de política controla qual porta é usada para RPC sobre TCP para conexões de entrada com o spooler de impressão e conexões de saída com spoolers de impressão remotos.

O uso de portas dinâmicas para impressão dificulta que um invasor saiba qual porta está sendo usada e, portanto, qual porta atacar.

Computer Configuration\Policies\Administrative Templates\Printers\Configure RPC over TCP port

<img width="1170" height="937" alt="image" src="https://github.com/user-attachments/assets/532b6488-17c6-4676-8a89-d5da33b5032e" />

Se o seu ambiente de impressão atual estiver configurado para uma porta TCP específica, essa configuração pode exigir uma alteração no firewall (se aplicável) para que a impressão continue.

Garanta que 'Configure RPC packet level privacy setting for incoming connections' esteja atribuido como 'Enabled'

 Esta configuração de política controla a privacidade em nível de pacote para conexões de entrada de Chamada de Procedimento Remoto (RPC).

Existe uma vulnerabilidade de bypass de segurança (CVE-2021-1678 | Vulnerabilidade de Spoofing do Spooler de Impressão do Windows) na forma como a associação RPC da impressora lida com a autenticação para a interface Winspool remota. Habilitar a configuração de privacidade em nível de pacote RPC para conexões de entrada força o servidor a aumentar o nível de autenticação para minimizar essa vulnerabilidade.

Computer Configuration\Policies\Administrative Templates\MS Security Guide\Configure RPC packet level privacy setting for incoming connections

<img width="1169" height="946" alt="image" src="https://github.com/user-attachments/assets/46ccb636-37ee-4653-8cb6-382bc042dff0" />

O hardening de infraestrutura Windows é um exercício de precisão: não se trata apenas de bloquear o que é óbvio, mas de refinar protocolos legados para que eles sobrevivam ao cenário de ameaças moderno. Implementar a privacidade em nível de pacote RPC e o dinamismo de portas é uma declaração de que a segurança da sua organização não aceita padrões de configuração inseguros por conveniência. O equilíbrio entre operabilidade e defesa é tênue, mas o reforço dessas camadas é o que diferencia uma rede vulnerável de uma infraestrutura resiliente.
