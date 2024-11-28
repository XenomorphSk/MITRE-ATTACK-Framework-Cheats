Procedimentos

Os procedimentos descrevem as ações detalhadas realizadas pelos atacantes para implementar uma técnica específica. Eles oferecem uma visão mais precisa e operacional sobre como uma técnica é executada na prática.
Exemplos de Procedimentos

    Procedimento de Phishing (Acesso Inicial)
        Passo 1: O atacante cria um email falsificado com um link para um site de phishing que se parece com um site legítimo (ex: página falsa de login bancário).
        Passo 2: O atacante envia o email para um grupo alvo, tentando enganar os usuários para que eles cliquem no link.
        Passo 3: Quando o usuário insere suas credenciais no site falso, o atacante coleta essas informações e as usa para acessar sistemas internos.
        Passo 4: O atacante pode usar essas credenciais para obter acesso inicial a redes ou serviços internos da vítima.

    Procedimento de Exploit de Dia Zero (Escalada de Privilégios)
        Passo 1: O atacante pesquisa vulnerabilidades conhecidas ou descobre uma falha de segurança em um sistema operacional ou aplicativo.
        Passo 2: Ele desenvolve ou adquire um exploit de zero-day para essa vulnerabilidade.
        Passo 3: O atacante utiliza o exploit para invadir o sistema e escalar privilégios, assumindo um papel de administrador ou root.
        Passo 4: Após escalar privilégios, o atacante pode ter acesso irrestrito a dados sensíveis ou outras partes do sistema.

    Procedimento de Uso de PowerShell (Execução)
        Passo 1: O atacante injeta um script malicioso no PowerShell do sistema comprometido.
        Passo 2: O script malicioso executa comandos para baixar outros malwares ou exfiltrar dados sensíveis.
        Passo 3: O script pode ser programado para ser executado automaticamente ou sob demanda, dando ao atacante controle contínuo sobre o sistema.
        Passo 4: A execução do PowerShell é muitas vezes encoberta por técnicas de ofuscação para evitar a detecção por ferramentas de segurança.

    Procedimento de Backdoor (Persistência)
        Passo 1: O atacante instala um backdoor, como Netcat ou Meterpreter, no sistema comprometido.
        Passo 2: O backdoor permite ao atacante se conectar ao sistema comprometido remotamente e manter o acesso.
        Passo 3: Após a instalação, o atacante pode alterar configurações de segurança, excluir logs ou modificar arquivos para manter a persistência.
        Passo 4: O backdoor pode ser configurado para reiniciar automaticamente após reinicializações do sistema, permitindo o acesso contínuo.

    Procedimento de Exfiltração via HTTPS (Exfiltração de Dados)
        Passo 1: O atacante coleta dados sensíveis, como credenciais ou informações financeiras, de sistemas comprometidos.
        Passo 2: Ele criptografa os dados para impedir que sejam detectados durante a transmissão.
        Passo 3: Os dados criptografados são enviados para um servidor de comando e controle (C2) através de uma conexão HTTPS.
        Passo 4: A exfiltração é realizada de forma oculta, aproveitando a natureza criptografada do protocolo HTTPS para evitar a detecção por ferramentas de monitoramento de rede.