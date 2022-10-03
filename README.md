# ansible-redis-sentinel

Ansible Playbook to deploy a High Availability Redis with Sentinel

## Getting started

1. Create 3 servers with public-key authentication
2. Copy `vars.yml.example` to `vars.yml`. Replace `<YOUR_PASSWORD>` with a secured password
3. Edit `inventory` filel and set the corresponding IP address for each server.
4. Run playbook `setup-redis-sentinel.yml`

    ```bash
    ansible-playbook setup-redis-sentinel.yml -i inventory
    ```

## Notice

The configuration for Redis and Sentinel are defined in `redis.conf.j2` and `sentinel.conf.j2`. The playbook explicitly uses `:` to separate each line and use `regexp` to update the corresponding file on the server. Therefore, the playbook will only touch the necessary setting and don't modify any other default settings.
