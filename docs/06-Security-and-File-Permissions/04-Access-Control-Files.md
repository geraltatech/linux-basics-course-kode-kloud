# ACCESS CONTROL FILES

Aquí tienes un resumen súper directo, limpio y estructurado, listo para copiar y pegar en tu repositorio de Git (por ejemplo, en un archivo `README.md` o tus notas):

---

# Control de Acceso en Linux (Resumen)

El control de acceso en Linux se gestiona a través de archivos de configuración clave que definen la identidad, los privilegios y los permisos de red en el sistema.

### 1. Gestión de Usuarios y Grupos

* **`/etc/passwd`**: Lista de cuentas de usuario, sus directorios base y shells asignados.
* **`/etc/shadow`**: Almacena las contraseñas cifradas y sus políticas de caducidad de forma segura.
* **`/etc/group`**: Define los grupos del sistema y sus miembros.

### 2. Privilegios de Administrador

* **`/etc/sudoers`**: Especifica qué usuarios o grupos pueden ejecutar comandos con privilegios de superusuario (`root`).

### 3. Seguridad de Red y Conexiones

* **`/etc/hosts.allow`**: Lista de hosts e IPs con acceso permitido a los servicios locales.
* **`/etc/hosts.deny`**: Lista de hosts e IPs bloqueados para los servicios locales.

### 4. Permisos Avanzados (ACLs y MAC)

* **ACLs (Listas de Control de Acceso)**: Permisos granulares aplicados directamente a archivos y carpetas para usuarios específicos.
* **SELinux / AppArmor**: Políticas de seguridad que restringen las acciones de procesos y usuarios (incluso de `root`).

  - Take me to the [Tutorial](https://kodekloud.com/topic/access-control-files/)
  
  - Access Ccontrol files are stored under **`/etc`**.
  - Can be read by anyone and can be only edited by **`root`** user.


  ### Control files

  - To get more details about one's account for example **`bob`** account, home director, uid, and shell check **`/etc/passwd`** 

    ```
    [~]$ grep -i ^bob /etc/passwd
    bob:x:1002:1002::/home/bob:/bin/sh
    USERNAME:PASSWORD:UID:GID:GECOS:HOMEDIR:SHELL
    ```
   
    ![passwd](../../images//passwd.PNG)

  - Password are stored under **`/etc/shadow`**

    ```
    [~]$ grep -i ^bob /etc/shadow
    bob:$6$0h0utOtO$5JcuRxR7y72LLQk4Kdog7u09LsNFS0yZPkIC8pV9tgD0wXCHutY
    cWF/7.eJ3TfGfG0lj4JF63PyuPwKC18tJS.:18188:0:99999:7:::

    USERNAME:PASSWORD:LASTCHANGE:MINAGE:MAXAGE:WARN:INACTIVE:EXPDATE
    ```

    ![shadow](../../images//shadow.PNG)

  - Check the groups **`bob`** belongs too

    ```
    [~]$ grep -i ^bob /etc/group
    NAME:PASSWORD:GID:MEMBERS
    ```

    ![egp](../../images//egp.PNG)

# HANDS-ON LABS

  - Lets start with Managing and User Accounts [here](https://kodekloud.com/courses/the-linux-basics-course/lectures/17074503)
