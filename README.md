# How to use

1. Login with root on your local machine
2. Create ssh key for root user

    ```bash
    ssh-keygen -o -a 100 -t ed25519 -C "you@yourdomain.email" -f /root/.ssh/id_ed25519
    ```

3. Copy te id_ed25519.pub content for remote user root on remote machine like

    ```bash
    # local
    scp /root/.ssh/id_ed25519.pub administrador@ip:/tmp/authorized_keys
    # remote
    cp /tmp/authorized_keys /root/.ssh/authorized_keys
    ```
4. install ansible

    ```bash
    apt install ansible sshpass -y
    ```
5. Run ansible playbook

    ```bash
    echo "[linuxdesktop]\n[ip]" >> /etc/ansible/hosts
    ansible-playbook ubuntu-linux-wcd.yaml -v
    ```

6. Input AD admin username
7. Input the password for AD admin
8. Input the DNS of domain like: testead.local
9. Input the DNS ips like: 192.168.1.200,192.168.1.201