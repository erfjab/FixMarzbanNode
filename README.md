# FixMarzbanNode

This guide helps you download `node.py` and configure it within Marzban.

## Steps

1. **Download `node.py`**  
   Download `node.py` from the repository to your Marzban directory:

   ```bash
   sudo wget -P /opt/marzban/ https://raw.githubusercontent.com/erfjab/FixMarzbanNode/refs/heads/master/node.py
   ```

2. **Edit `docker-compose.yml`**  
   Open your `docker-compose.yml` file in the editor:

   ```bash
   nano /opt/marzban/docker-compose.yml
   ```

3. **Add Volume Configuration**  
   In the `volumes` section, add the following lines to link `node.py`:

   ```yaml
   volumes:
     - /var/lib/marzban:/var/lib/marzban   
     - /opt/marzban/node.py:/code/app/xray/node.py
   ```

4. **Restart Marzban**  
   To apply changes, restart Marzban:

   ```bash
   marzban restart
   ```

All done! Marzban is now configured with the `node.py` file.