ssh-keygen -t ed25519 -C <meu_email>

# PARA PEGAR A FRASE E COPIAR NO GITLAB / GITHUB
code ~/.ssh/id_ed25519.pub


# CRIAR ESSA CONFIG DA SSH:

#### sudo nano ~/.ssh/config

Host github.com
User git
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 443

Host gitlab.com
Hostname altssh.gitlab.com
User git
Port 443
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa


#PARA ADICIONAR AO CONFIAVEIS
ssh -T git@gitlab.com
ssh -T git@github.com
