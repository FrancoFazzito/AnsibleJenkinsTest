## Project Structure

- `inventory.ini`: Inventory files for the host server.
- `playbooks/`: Directory for playbooks and task files.
  - `tasks/`: Directory for individual task files.
  - `handlers/`: Directory for handler files.
- `templates/`: Directory for template files.
- `README.md`: Project description and instructions.

## Usage

1. Update the `inventory` files with your server details.
2. Run the playbook:

```sh
ansible-playbook -i inventory.ini playbooks/site.yml
```

## Jenkins

Para poder hacer uso del jenkins file tan solo se tendria que crear un nuevo pipeline referenciando a este archivo y ejecutar este dentro del ansible controller con su correspondiente configuracion de SSH hacia el host

```mermaid
graph TD
    Actor -->|Trigger| RepoPlaybook
    RepoPlaybook -->|Fetch| Jenkinsfile
    Jenkinsfile -->|Load| Jenkins
    Jenkins -->|Run| ControllerAgent
    ControllerAgent -->|Deploy| Node1
    
    classDef repoPlaybook fill:#f9f,stroke:#333,stroke-width:2px;
    classDef controllerAgent fill:#bbf,stroke:#333,stroke-width:2px;
    classDef node1 fill:#bfb,stroke:#333,stroke-width:2px;

    RepoPlaybook:::repoPlaybook
    ControllerAgent:::controllerAgent
    Node1:::node1

