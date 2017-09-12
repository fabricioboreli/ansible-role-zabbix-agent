Ansible Role Skeleton
=====================
Esqueleto/Modelo de estrutura de diretórios para criação de role Ansible.


Requisitos
----------
Nenhum / Debian 8

Variaveis do Role
-----------------
Descrição das variaveis:

```yaml
codigo_yaml: variavel_content
```

Dependências
------------
Não depende de nenhum outro role.

Playbook de exemplo
-------------------
```yaml
- name: Role name
  hosts: server
  become: true
  gather_facts: true

  roles:
    - role: roles_name
```

Licença
-------
MIT

Informações do Autor
--------------------
Fabricio Boreli Ferreira  
