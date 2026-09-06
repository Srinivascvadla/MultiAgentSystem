# MultiAgentSystem

## Description

MultiAgentSystem is a framework for building and managing multi-agent systems. It provides tools and abstractions to simplify the development of complex, distributed agent-based applications.

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/your-repo.git
cd your-repo

# (Optional) Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

# Install the package and its dependencies
pip install -e .
```

## Usage Examples

```python
from multiagentsystem import Agent, System

# Define a simple agent
class EchoAgent(Agent):
    def on_message(self, message):
        print(f"EchoAgent received: {message}")
        self.send(message)

# Create a system and add agents
system = System()
agent = EchoAgent(name="echo")
system.add_agent(agent)

# Start the system
system.start()

# Send a message to the agent
system.send_message("echo", "Hello, world!")
```

For more detailed examples, see the `examples/` directory.

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix:
   ```bash
   git checkout -b my-feature-branch
   ```
3. Make your changes and ensure the code passes any existing tests.
4. Commit your changes with a clear commit message.
5. Push to your fork and open a Pull Request.

Please adhere to the existing code style and include tests for new functionality when appropriate.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.