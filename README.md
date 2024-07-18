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
    
    subgraph Repo::Playbook
        RepoPlaybook
    end
    
    subgraph Controller::Agent
        ControllerAgent
    end
    
    subgraph Node1
        Node1
    end
```
