Personal Dotfiles made originally for void linux

Install the needed packages:
'''bash
sudo xbps-install -Sy waybar wofi neovim pywal swww mesa mesa-dri seatd sddm dbus xdg-desktop-portal-hyprland

Hyprland case:
# Add the Hyprland community repo
echo "repository=https://raw.githubusercontent.com/Makrennel/hyprland-void/repository-x86_64-glibc" | sudo tee /etc/xbps.d/hyprland-void.conf

# Sync and install
'''bash
sudo xbps-install -S hyprland xdg-desktop-portal-hyprland

# Enable DBus and Seatd (Required for Wayland/Hyprland)
'''bash
sudo ln -s /etc/sv/dbus /var/service/
sudo ln -s /etc/sv/seatd /var/service/
sudo ln -s /etc/sv/sddm /var/service/

# Add yourself to the seatd group
'''bash
sudo usermod -aG wheel disk audio video storage network kvm input dbus polkitd _seatd fuse $(whoami)
