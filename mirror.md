sudo pacman -Syu reflector

sudo reflector --verbose --country Brazil --protocol https --sort rate --save /etc/pacman.d/mirrorlist

