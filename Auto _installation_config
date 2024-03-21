#!/bin/bash

# Function to install packages using apt
install_apt() {
    sudo apt update
    sudo apt install -y i3 polybar picom kitty alacritty dmenu xfce4-appfinder powerline
}

# Function to install packages using pacman
install_pacman() {
    sudo pacman -Syu --noconfirm
    sudo pacman -S --noconfirm i3-wm polybar picom kitty alacritty dmenu xfce4-appfinder powerline
}

# Function to prompt user for Linux distribution
prompt_distribution() {
    echo "Which Linux distribution are you using?"
    select distro in "Debian/Ubuntu" "Arch/Manjaro" "Other"; do
        case $distro in
            "Debian/Ubuntu")
                install_apt
                break
                ;;
            "Arch/Manjaro")
                install_pacman
                break
                ;;
            "Other")
                echo "Please install the required packages manually for your distribution."
                break
                ;;
            *)
                echo "Invalid selection. Please try again."
                ;;
        esac
    done
}

# Function to copy and replace config files
copy_configs() {
    sudo cp -r dotfiles/* ~/.config/
    echo "Config files copied and replaced successfully."
}

# Main function
main() {
    prompt_distribution
    copy_configs
}

main
