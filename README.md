# MultiAgentSystem

## Overview

**MultiAgentSystem** is a lightweight, extensible framework for building and orchestrating multiple autonomous agents that can collaborate, communicate, and solve complex problems together. It provides a simple API to define agents, their behaviors, and interaction protocols, making it easy to prototype and deploy multi‑agent solutions in Python.

## Features

- **Modular Architecture** – Define agents, environments, and communication channels as interchangeable components.
- **Flexible Communication** – Support for direct messaging, broadcast, and shared knowledge bases.
- **Scalable Execution** – Run agents synchronously or asynchronously with optional multiprocessing.
- **Extensible** – Plug‑in custom policies, learning algorithms, or external services.
- **Built‑in Tools** – Logging, monitoring, and visualization utilities.

## Installation

```bash
# Using pip
pip install multiagentsystem
```

> **Note:** The package requires Python 3.8 or newer.

## Quick Start

Below is a minimal example that creates two agents that exchange greetings.

```python
from multiagentsystem import Agent, Message, System

# Define simple agent behavior
class GreeterAgent(Agent):
    async def on_message(self, msg: Message):
        if msg.content == "hello":
            await self.send(Message(to=msg.sender, content="hi there!"))

# Instantiate agents
alice = GreeterAgent(name="Alice")
bob = GreeterAgent(name="Bob")

# Create a system and add agents
system = System()
system.add_agent(alice)
system.add_agent(bob)

# Start the interaction
await system.start()
await alice.send(Message(to="Bob", content="hello"))
```

### Running the Example

Save the script as `example.py` and run:

```bash
python example.py
```

You should see the agents exchanging messages printed to the console.

## Documentation

Full API reference and advanced tutorials are available at:

- https://github.com/yourusername/MultiAgentSystem/wiki
- https://yourusername.github.io/MultiAgentSystem/

## Contributing

Contributions are welcome! Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to submit pull requests, report bugs, or propose new features.

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

*Happy coding with MultiAgentSystem!*