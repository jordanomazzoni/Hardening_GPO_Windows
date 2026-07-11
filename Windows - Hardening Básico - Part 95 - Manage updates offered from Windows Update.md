![](https://media.licdn.com/dms/image/v2/D4D12AQHhEF-8m1uJZg/article-cover_image-shrink_720_1280/B4DZ4tj.RkGQAQ-/0/1778880867673?e=1785369600&v=beta&t=LQLwlPljxN1RUq1zQl1sdmyTSt45Jj428LCZLy953Jc)

# Windows - Hardening Básico - Part 95 - Manage updates offered from Windows Update

Garanta que 'Manage preview builds' esteja atribuido como 'Disabled'

Essa configuração de política gerencia quais atualizações são recebidas antes do lançamento oficial.

Canal Dev: Ideal para usuários com alto nível de conhecimento técnico. Os participantes do programa Insider no Canal Dev receberão versões da nossa ramificação de desenvolvimento ativa, a mais antiga no ciclo de desenvolvimento. Essas versões não correspondem a uma versão específica do Windows 10.

Canal Beta: Ideal para quem deseja explorar os recursos futuros do Windows 10. Seu feedback será especialmente importante aqui, pois ajudará nossos engenheiros a garantir que os principais problemas sejam corrigidos antes de um lançamento importante.

Canal Release Preview (padrão): Os participantes do programa Insider no Canal Release Preview terão acesso à próxima versão do Windows 10 antes do lançamento oficial. Essas versões são suportadas pela Microsoft. Recomendamos que as empresas testem e validem as próximas versões do Windows 10 antes da implementação em larga escala em suas organizações por meio do Canal Release Preview.

O estado recomendado para essa configuração é: Desativado.

Permitir recursos experimentais em um ambiente corporativo gerenciado pode ser arriscado, pois pode introduzir bugs e falhas de segurança nos sistemas, facilitando o acesso de invasores. Geralmente, é preferível usar apenas versões prontas para produção.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:

```
* Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Update\\Manage updates offered from Windows Update\\Manage preview builds
```


![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQGGYZQ1aU_21Q/article-inline_image-shrink_1500_2232/B4DZ4tkDbDJYAQ-/0/1778880886834?e=1785369600&v=beta&t=HC2i6UrAOmPhB48GAJfOhSZ4PG-i31sJQXNdJbHlsDY)

Garanta que 'Select when Quality Updates are received' esteja atribuido como 'Enabled: 0 days'

Esta configuração controla quando as Atualizações de Qualidade são recebidas.

O estado recomendado para esta configuração é: Ativado: 0 dias.

Observação: Se a política "Permitir Dados de Diagnóstico" (anteriormente "Permitir Telemetria") estiver definida como 0, esta política não terá efeito.

As Atualizações de Qualidade podem conter correções de bugs importantes e/ou patches de segurança e devem ser instaladas o mais rápido possível.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: 0 dias:



* ```
  * Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Update\\Manage updates offered from Windows Update\\Select when Quality Updates are received
  ```

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQFLrE75JKr6YA/article-inline_image-shrink_1000_1488/B4DZ4tkWV4KAAI-/0/1778880964309?e=1785369600&v=beta&t=ff9-0DbDGyr4Qf407QKwJJqT5fM_8hLpne9fcpfpQDs)

Garanta que 'Enable optional updates' esteja atribuido como 'Disabled'

Essa configuração de política controla se os dispositivos podem receber atualizações opcionais (incluindo a Implantação Controlada de Recursos (CFRs)). Essas atualizações opcionais podem incluir atualizações não relacionadas à segurança, aprimoramentos de recursos e outras melhorias.

O estado recomendado para essa configuração é: Desativado.

Frequentemente, novos recursos ou aprimoramentos ativados por padrão (antes que os administradores de TI estejam prontos para gerenciá-los) podem impactar negativamente a experiência do usuário ou introduzir bugs e riscos de segurança.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:



* ```
  * Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\Windows Update\\Manage updates offered from Windows Update\\Enable optional updates
  ```

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQG7Y4jLmzmPpg/article-inline_image-shrink_1500_2232/B4DZ4tklC8IMAQ-/0/1778881024536?e=1785369600&v=beta&t=XOVWetCDvohLW5s1ZeWamjaSVobh0l2TJi5EZCGN-bk)

Salve este post como parte do seu checklist de hardening Windows.
