#!/usr/bin/env bash
set -e

echo "🚀 Updating system..."
sudo pacman -Syu

echo "🚀 Installing KDE Plasma minimal environment..."
sudo pacman -S --needed plasma dolphin konsole \
plasma-systemmonitor kde-gtk-config kvantum qt5ct qt6ct papirus-icon-theme \
plasma-integration 

echo "🚀 Installing LightDM and GTK greeter..."
sudo pacman -S --needed lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings

echo "🚀 Installing Hyprland + swww for wallpapers..."
sudo pacman -S --needed hyprland swww

echo "🚀 Installing ZSH + plugins..."
sudo pacman -S --needed zsh zsh-autosuggestions zsh-syntax-highlighting

echo "🚀 Installing konsave via yay from AUR..."
yay -S --noconfirm konsave

echo "🚀 Changing default shell to zsh..."
chsh -s $(which zsh)

echo "🚀 Enabling LightDM..."
sudo systemctl enable lightdm

echo "🚀 Downloading your dotfiles and applying themes..."
cd ~
curl -LO https://github.com/VeniVediVeci96/dotfiles/releases/latest/download/dotfiles_theme.zip
unzip -o dotfiles_theme.zip
cd dotfiles_theme
./install-theme.sh

echo "🚀 Downloading and applying your konsave theme..."
cd ~
curl -LO https://github.com/VeniVediVeci96/dotfiles/releases/latest/download/CyberOrange_konsave.zip
unzip -o CyberOrange_konsave.zip
konsave -i CyberOrange_konsave/CyberOrange.knsv
konsave -a CyberOrange

echo "🚀 Downloading and installing your Konsole color scheme..."
curl -LO https://github.com/VeniVediVeci96/dotfiles/releases/latest/download/CyberOrange_Konsole.zip
unzip -o CyberOrange_Konsole.zip
mkdir -p ~/.local/share/konsole
cp konsole_colors/CyberOrange.colorscheme ~/.local/share/konsole/

echo "✅ DONE! Reboot to start using LightDM, Plasma or Hyprland. Enjoy your CyberOrange theme!"
