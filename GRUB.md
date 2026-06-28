Para alterar o tempo de espera do GRUB no Arch Linux, edite o arquivo de configuração principal e gere novamente o arquivo .cfg.
<p>Siga este procedimento direto: Abra o arquivo /etc/default/grub com um editor de texto (como nano) usando privilégios de administrador:

<p></p>bash sudo nano /etc/default/grub
<p>Use o código com cuidado. <p>

</p>Localize a linha GRUB_TIMEOUT=X (onde X é o tempo em segundos) e altere para o valor desejado.
<p></p>Para pular a tela de menu sem atrasos, use 0; para aguardar indefinidamente pela escolha do usuário, use -1.Salve e feche o arquivo. 
<p></p>Se estiver no Nano, pressione Ctrl+O e depois Enter para confirmar, e Ctrl+X para sair.Gere novamente o arquivo de configuração principal do GRUB para que as alterações entrem em vigor:
<p></p>sudo grub-mkconfig -o /boot/grub/grub.cfg
<p></p>Use o código com cuidado.
<p>curl -fsSL https://christitus.com/linux | sh</p>
<p>sudo nano /etc/mkinitcpio.conf

