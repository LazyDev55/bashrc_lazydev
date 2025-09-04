# Aliases útiles para sistema

## Alias de sistema básicos

```bash
alias apa='~/.actualizar.sh && systemctl poweroff' 
alias rei='systemctl reboot' 
alias ping='ping 8.8.8.8' 
alias act='~/.actualizar.sh' 
alias sus='systemctl suspend'
```

## Descripción de los alias

- **`apa`**: Ejecuta el script de actualización y apaga el sistema
- **`rei`**: Reinicia el sistema
- **`ping`**: Realiza ping al servidor DNS de Google (8.8.8.8)
- **`act`**: Ejecuta el script de actualización del sistema
- **`sus`**: Suspende el sistema

## Alias avanzado para i3wm

```bash
# Versión para i3 con bloqueo de pantalla elegante
alias sus='scrot /tmp/screen_locked.png && \
           convert /tmp/screen_locked.png -blur 0x12 /tmp/screen_blurred.png && \
           i3lock -i /tmp/screen_blurred.png && \
           rm /tmp/screen_locked.png /tmp/screen_blurred.png && \
           systemctl suspend'
```

### Requisitos para el alias de i3:
- `scrot` para capturar pantalla
- `imagemagick` para el efecto de desenfoque
- `i3lock` para bloquear la pantalla

## Instalación

Agrega estos alias a tu archivo `.bashrc` o `.zshrc`:

```bash
echo '
# Aliases de sistema
alias apa='"'"'~/.actualizar.sh && systemctl poweroff'"'"'
alias rei='"'"'systemctl reboot'"'"'
alias ping='"'"'ping 8.8.8.8'"'"'
alias act='"'"'~/.actualizar.sh'"'"'
alias sus='"'"'systemctl suspend'"'"'

# Alias para i3 (descomentar si se usa i3)
# alias sus='"'"'scrot /tmp/screen_locked.png && convert /tmp/screen_locked.png -blur 0x12 /tmp/screen_blurred.png && i3lock -i /tmp/screen_blurred.png && rm /tmp/screen_locked.png /tmp/screen_blurred.png && systemctl suspend'"'"'
' >> ~/.bashrc
```

## Notas
- Asegúrate de que el script `~/.actualizar.sh` exista y tenga permisos de ejecución
- El alias para i3 requiere paquetes adicionales instalados
- Modifica según tus necesidades específicas
