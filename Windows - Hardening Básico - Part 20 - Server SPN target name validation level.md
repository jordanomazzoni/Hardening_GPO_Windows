<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/c591b966-8631-44c0-a357-180b1c4b6a1e" />


# Windows - Hardening Básico - Part 20 - Server SPN target name validation level

O protocolo SMB, base para o compartilhamento de arquivos e impressoras, é historicamente um dos vetores favoritos de atores maliciosos para movimentação lateral e ataques de SMB Relay.

Aumentar o rigor na validação do Service Principal Name (SPN) é implementar uma camada crítica de defesa que impede que um atacante intercepte e retransmita autenticações dentro da sua rede.

O Service Principal Name é um identificador exclusivo para uma instância de serviço. No caso do SMB, quando você tenta acessar \\FileServer, o seu computador gera um SPN do tipo cifs/FileServer.

Esse identificador serve para que o Kerberos (ou NTLM) saiba exatamente com qual serviço e conta de computador ele está tentando se autenticar.

Essa configuração de política controla o nível de validação que um computador com pastas ou impressoras compartilhadas (o servidor) realiza no nome principal de serviço (SPN) fornecido pelo computador cliente ao estabelecer uma sessão usando o protocolo SMB (Server Message Block).

O protocolo SMB fornece a base para o compartilhamento de arquivos e impressoras e outras operações de rede, como a administração remota do Windows. O protocolo SMB valida o nome principal de serviço (SPN) do servidor SMB no bloco de autenticação fornecido por um cliente SMB para evitar um tipo de ataque contra servidores SMB conhecido como ataque de retransmissão SMB. Essa configuração afetará tanto o SMB1 quanto o SMB2.

Garanta que a configuração 'Microsoft network server: Server SPN target name validation level' esteja atribuída como 'Accept if provided by client' ou superior

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Microsoft network server: Server SPN target name validation level

<img width="1119" height="840" alt="image" src="https://github.com/user-attachments/assets/a37f717e-1d1d-41dd-8f8a-7645cb0b4edd" />

Accept if provided by client – o servidor SMB aceitará e validará o SPN fornecido pelo cliente SMB e permitirá o estabelecimento de uma sessão se este corresponder à lista de SPNs do próprio servidor SMB. Se o SPN NÃO corresponder, a solicitação de sessão para esse cliente SMB será negada. (Se você me enviou um nome de destino (SPN), eu vou conferir se sou eu mesmo. Se não for, eu bloqueio).

Required from client – o cliente SMB DEVE enviar um nome SPN na configuração da sessão, e o nome SPN fornecido DEVE corresponder ao servidor SMB ao qual está sendo solicitada a conexão. Se nenhum SPN for fornecido pelo cliente, ou se o SPN fornecido não corresponder, a sessão será negada. (Eu exijo que você me diga para quem essa mensagem foi enviada. Se você não enviar o SPN ou se o nome não for o meu, a conexão será negada)

Off (Padrão em sistemas antigos): O servidor ignora o SPN. Se a senha bater, o acesso é liberado. É o cenário ideal para o atacante.

Optar pelo nível de validação "Required from client" é uma decisão estratégica: você deixa de apenas "aceitar" o que o cliente envia para "exigir" a prova de identidade correta. Experimente e homologue as configurações possíveis para elevar a maturidade de segurança do ambiente.

Salve este post como parte do seu checklist de hardening Windows.
