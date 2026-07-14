<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f0a60e76-954b-4588-a5cc-8d9476216ab2" />


# Windows - Hardening Básico - Part 48 - RPC Endpoint Mapper Client Authentication - Restrict Unauthenticated RPC clients

Garanta que 'Enable RPC Endpoint Mapper Client Authentication' esteja atribuido como 'Enabled' 

Essa configuração de política controla se os clientes RPC se autenticam com o Endpoint Mapper Service quando a chamada que estão fazendo contém informações de autenticação. O Windows exige que o cliente RPC se identifique (autentique) antes que o EPM forneça a porta do serviço solicitado, desde que a chamada já contenha informações de autenticação. Pontos fortes desta configuração:

Dificulta a Enumeração
Mitiga o Vazamento de Informações: Consultas anônimas ao RPC
Higiene de Protocolo: avaliar se faz sentido permitir entidades não autenticadas de estabelecer comunicação



Computer Configuration\Policies\Administrative Templates\System\Remote Procedure Call\Enable RPC Endpoint Mapper Client Authentication

<img width="1264" height="846" alt="image" src="https://github.com/user-attachments/assets/5492b8e8-eaa0-479c-9f41-1687986da15e" />

Garanta que 'Restrict Unauthenticated RPC clients' esteja atribuido como 'Enabled: Authenticated'

Essa configuração de política controla como o ambiente de execução do servidor RPC lida com clientes RPC não autenticados que se conectam aos servidores RPC.

Essa configuração de política afeta todos os aplicativos RPC. Em um ambiente de domínio, essa configuração de política deve ser usada com cautela, pois pode afetar uma ampla gama de funcionalidades, incluindo o próprio processamento de políticas de grupo. Reverter uma alteração nessa configuração de política pode exigir intervenção manual em cada máquina afetada. Essa configuração de política nunca deve ser aplicada a um Controlador de Domínio.

Um cliente será considerado autenticado se usar um pipe nomeado para se comunicar com o servidor ou se usar a Segurança RPC. Interfaces RPC que solicitaram especificamente acesso por clientes não autenticados podem ser isentas dessa restrição, dependendo do valor selecionado para essa configuração de política.

"None" permite que todos os clientes RPC se conectem aos servidores RPC em execução na máquina em que a configuração da política é aplicada.
"Authenticated" permite que apenas clientes RPC autenticados (conforme a definição acima) se conectem aos servidores RPC em execução na máquina em que a configuração da política é aplicada. Exceções são concedidas às interfaces que as solicitaram.
"Authenticated without exceptions" permite que apenas clientes RPC autenticados (conforme a definição acima) se conectem aos servidores RPC em execução na máquina em que a configuração da política é aplicada. Nenhuma exceção é permitida. Este valor pode causar problemas graves e não é recomendado.

Esta configuração de política não será aplicada até que o sistema seja reinicializado.

O estado recomendado para esta configuração é: Ativado: Autenticado

A comunicação RPC não autenticada pode criar uma vulnerabilidade de segurança.

Computer Configuration\Policies\Administrative Templates\System\Remote Procedure Call\Restrict Unauthenticated RPC clients

<img width="1266" height="847" alt="image" src="https://github.com/user-attachments/assets/b455ada9-c6f9-46b5-9fd5-c84ed03a5263" />

Salve este post como parte do seu checklist de hardening Windows.
