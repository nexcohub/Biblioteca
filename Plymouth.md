Para remover o Plymouth no Arch Linux 
<p></p>
<p>Para remover o Plymouth no Arch Linux completamente, é preciso desinstalar o pacote, limpar a inicialização no initramfs e remover o parâmetro splash do gerenciador de boot (como o GRUB).Passo 1: Remover o pacoteAbra o seu terminal e utilize o pacman para remover o plymouth e suas dependências:
  
  sudo pacman -Rcns plymouth
  
Passo 2: Remover do Initramfs
Edite o arquivo de configuração do mkinitcpio com seu editor preferido (por exemplo, nano):

sudo nano /etc/mkinitcpio.conf


Procure pela linha que começa com HOOKS=.Remova a palavra plymouth dessa lista. Salve o arquivo e saia (no nano, aperte Ctrl+O, Enter e depois Ctrl+X).

Passo 3: Reconstruir o Initramfs Reconstrua as imagens do sistema com o comando:

sudo mkinitcpio -P

Passo 4: Atualizar o Gerenciador de Boot (Ex: GRUB)Se você utiliza o GRUB, é necessário remover a opção de splash da inicialização para que o boot fique limpo e em modo texto:
Abra o arquivo de configuração do GRUB:

sudo nano /etc/default/grub

Procure pela linha GRUB_CMDLINE_LINUX_DEFAULT="...".Remova a palavra splash de dentro das aspas. Salve e saia do arquivo. Atualize a configuração do GRUB com:

sudo grub-mkconfig -o /boot/grub/grub.cfg

Se você utiliza outro gerenciador (como systemd-boot), precisará remover o parâmetro splash ou plymouth. enable=0 diretamente no arquivo de configuração do seu bootloader na pasta /efi/loader/entries/.
Você está tendo algum problema específico com o Plymouth na hora de inicializar o sistema? Caso enfrente algum erro ao reiniciar, posso te ajudar a verificar as configurações do boot do seu Arch.
