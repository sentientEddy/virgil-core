
# Virgil Configuration Files

This directory contains core configuration files for the Virgil project. These files define trigger conditions, system parameters, and behavioral logic for the Vigilant Core.

## Files

- `vigilance_config.yaml`  
  Main system configuration file. Defines system name, logging behavior, action thresholds, confidence levels, and runtime preferences.

- `trigger_matrix.json`  
  Contains categorized semantic triggers, descriptions, detection guidance, confidence weights, and associated system actions. This file is central to Virgil’s ethical response logic.

## Usage

Configuration files are loaded at runtime by the Virgil core application. They can be modified to adjust sensitivity, change system responses, or expand detection coverage.

Ensure that changes maintain compatibility with any schema used in your runtime environment.

## Example

To load the YAML configuration in Python:

```python
import yaml

def load_config(path="config/vigilance_config.yaml"):
    with open(path, 'r') as f:
        return yaml.safe_load(f)

config = load_config()
print(config["system_name"])
```

## Notes

- All trigger matching is semantic, not keyword-based.
- Triggers should be tested against both benign and malicious input before deployment.
- Make backups before modifying core configuration files.
