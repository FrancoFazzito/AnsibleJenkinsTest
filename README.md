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