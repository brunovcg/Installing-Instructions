ssh-keygen -t ed25519 -C <meu_email>

# PARA PEGAR A FRASE E COPIAR NO GITLAB / GITHUB
code ~/.ssh/id_ed25519.pub


#PARA ADICIONAR AO CONFIAVEIS
ssh -T git@gitlab.com
ssh -T git@github.com
