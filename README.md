WordPress+Nginx+PHP-FPM Deployment on CentOS7

Inicialmente:

Este Playbook implementa de forma simples o WordPress, Interface Web do NGINX e gerenciador PHP. Para usar, edite o arquivo "hosts" para incluir o IP do servidor ao qual deseja implantar, garantindo ssh livre entre localhost e servidor remoto (adicionando a chave do seu localhost no servidor remoto) > (ssh-keygen > cd .ssh > vim id_rsa.pub > Copie a chave no servidor remoto, em: .ssh/authorized_keys).

1. Faça git clone deste repositório em seu localhost.
2. Edite o arquivo hosts (com o seu servidor, obviamente).
3. No caminho 'automated_wordpress/roles/defaults/main.yml' altere o '{{ server_hostname }}' para o IP do seu servidor ou DNS.  

E rode o Playbook assim:

"ansible-playbook -i hosts playbook.yml"

Resumidamente, este Playbook irá configurar o MySQL, WordPress, NGINX e PHP.

Quando rodar completamente, você terá acesso a tela inicial de configuração do WordPress.

Idéias para melhoria:

Automatizar chaves de acesso com "Common"

Separar os componentes (NGINX, PHP, MYSQL) em hosts diferentes e manipular a configuração conforme necessidade.

Criar tabelas no banco para administração de mais de um WordPress.
