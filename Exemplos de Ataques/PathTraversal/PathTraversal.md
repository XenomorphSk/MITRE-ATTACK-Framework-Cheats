Introdução ao Path Traversal (Transversal de Caminho)

O Path Traversal (ou Directory Traversal) é uma técnica de exploração usada por atacantes para acessar arquivos e diretórios fora do local autorizado dentro de um sistema de arquivos. Esse tipo de ataque ocorre quando uma aplicação não valida corretamente os parâmetros de entrada, permitindo que o atacante manipule o caminho de diretórios e acesse áreas sensíveis ou restritas, que de outra forma estariam protegidas.
Como Funciona o Path Traversal?

A exploração de Path Traversal acontece quando um atacante consegue manipular as entradas de dados para navegar para diretórios acima do diretório permitido, geralmente utilizando caracteres especiais como ../ ou variantes codificadas. A ideia é que, ao fornecer uma sequência manipulada, o atacante consiga acessar informações confidenciais ou executar operações maliciosas no sistema.
Exemplo Comum de Path Traversal

Um exemplo típico é o uso da sequência ../ para subir um nível na estrutura de diretórios e acessar arquivos sensíveis, como:

http://example.com/download.php?file=../../../../etc/passwd

No exemplo acima, o atacante manipula o parâmetro file para que a aplicação acesse um arquivo crítico do sistema (/etc/passwd no caso de sistemas Linux), que pode conter informações de usuários e senhas.
Métodos de Bypass de Filtros

Ataques de Path Traversal podem ser mais complexos se a aplicação tentar bloquear os caracteres suspeitos. Porém, existem diversas maneiras de contornar esses filtros, como:
Codificação de URL

Os atacantes podem usar a codificação de URL para mascarar os caracteres ../ e contornar as verificações de segurança, por exemplo:

    ../ pode ser codificado como %2e%2e%2f ou %252e%252e%252f.

Substituição de Caracteres

Outra técnica é substituir os caracteres de caminho por outros símbolos ou codificações. Por exemplo:

    O ponto . pode ser substituído por %u002e (em codificação Unicode).
    A barra / pode ser substituída por %u2215 ou %c0%af (em Unicode e UTF-8).

Duplicação de Sequências

Se a aplicação simplesmente remover os caracteres ../, o atacante pode duplicá-los:

    ..././ ou ...\.\ para burlar a validação.

Codificação Dupla

Em alguns casos, a codificação dupla pode ser utilizada para contornar mecanismos de filtro:

    ../ pode se tornar %252e%252e%252f, onde a primeira codificação %25 corresponde ao sinal %.

Exemplos de Bypass

    UNC Bypass: Um atacante pode injetar um compartilhamento UNC (Universal Naming Convention) para redirecionar o acesso a locais arbitrários:

\\localhost\c$\windows\win.ini

NGINX/ALB Bypass: Em algumas configurações do NGINX ou balanceadores de carga (ALB), é possível bloquear ataques de path traversal. Para contornar isso, o atacante pode adicionar múltiplas barras /:

http://nginx-server////////../../

ASP.NET Cookieless Session Bypass: Quando o session state cookieless está ativado, o ID de sessão é incorporado na URL, o que pode ser explorado para acessar diretórios ou arquivos proibidos:

    http://example.com/(S(x))/admin/(S(x))/main.aspx

Arquivos Interessantes em Sistemas Linux e Windows

Em ataques de Path Traversal, os atacantes frequentemente visam arquivos críticos do sistema. Alguns exemplos incluem:
Arquivos em Linux:

    /etc/passwd: Contém informações de usuários do sistema.
    /etc/shadow: Contém senhas criptografadas dos usuários.
    /var/log/apache/access.log: Arquivo de log de acesso do Apache.

Arquivos em Windows:

    c:\windows\system32\license.rtf
    c:\system32\inetsrv\metabase.xml
    c:\windows\repair\samb

Conclusão

O Path Traversal é um ataque perigoso que pode resultar em acesso não autorizado a arquivos e dados sensíveis. Proteger-se contra esse tipo de vulnerabilidade exige a validação rigorosa das entradas de dados, o uso de boas práticas de segurança na programação e a aplicação de filtros adequados para impedir a exploração de caminhos não autorizados.