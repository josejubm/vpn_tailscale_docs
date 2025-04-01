# Instalación de Tailscale VPN y Configuración del Laboratorio en Linux

## Instalación de Tailscale
Para instalar Tailscale, ejecuta el siguiente comando:

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

## Configuración de Tailscale

Para conectarse a la VPN, ejecuta el siguiente comando con una clave de autenticación válida:

```bash
sudo tailscale up --auth-key=tskey-auth-k4XPGNpnvd11CNTRL-CVT8mzrYNdei2CTBS59jbkeswwwswsws
```

>[!NOTE]
>Asegúrate de reemplazar la clave con una válida generada desde el panel de administración de Tailscale.

### Verificación de la Instalación
Para verificar que Tailscale está funcionando correctamente y obtener la lista de direcciones IP de la VPN, usa:

```bash
tailscale status
```

## Configuración del Archivo `/etc/hosts` para el Laboratorio
Para facilitar el acceso a los servidores del laboratorio, añade las siguientes líneas al archivo `/etc/hosts`:

```bash
#/etc/hosts

# Laboratorio
10.0.0.103 rhvh03.ansible-labs.com rhvh03
10.0.0.104 rhvh04.ansible-labs.com rhvh04
10.0.0.101 rhvh01.ansible-labs.com rhvh01  # Host principal
#10.0.0.99 rhvm02.ansible-labs.com rhvm02  # Manager (comentado)
100.116.237.73 rhvm02.ansible-labs.com rhvm02  # Manager activo

# GitLab
100.119.217.101 gitlab-hub.com gitlab-hub
100.117.125.94 idm.ansible-labs.com idm
```

>[!NOTE]
> Asegúrate de que las IPs sean correctas y reflejen la configuración real del laboratorio.

