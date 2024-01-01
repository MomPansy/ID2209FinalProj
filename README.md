# Dutch Auction Simulation Project README

## Overview
This project simulates a Dutch auction using OpenAI's language model (LLM) agents. It features one auctioneer and three participants, with an additional helper agent managing the responses of the participants. The simulation is designed to showcase the interaction between AI agents in an auction scenario, leveraging the capabilities of OpenAI's GPT-4 model.

## Project Structure
- `AuctioneerAgent`: Represents the auctioneer in the auction, responsible for controlling the auction flow and deciding when an item is sold.
- `GuestAgent`: Represents a participant in the auction, each with a unique bidding strategy.
- `Simulation`: Manages the overall auction process, coordinating between the auctioneer and the guests.
- `compare_ask_bid`: A utility function to compare the ask price and bid price.

## Dependencies
- OpenAI Python Library
- Python's `random` and `json` modules

## Setup
Before running the simulation, ensure that you have the OpenAI Python library installed and configured with your API key.

```python
from openai import OpenAI
client = OpenAI(api_key='YOUR_API_KEY')
```

## Classes Description
### AuctioneerAgent
- Initializes with a starting price and generates auction messages.
- Lowers the ask price if no bids are placed.
- Declares the item sold when a bid is accepted.

### GuestAgent
- Each guest is initialized with a random bid price.
- Decides whether to place a bid based on the current ask price.

### Simulation
- Orchestrates the auction process by aggregating responses from all guests and passing them to the auctioneer.

## Running the Simulation
1. Initialize the `AuctioneerAgent` and `GuestAgent`s.
2. Create a `Simulation` instance with the guests.
3. Run a loop to simulate auction rounds until the item is sold or a maximum number of rounds is reached.

```python
Auctioneer = AuctioneerAgent(name='John')
guests = [GuestAgent(name='Terry'), GuestAgent(name='Nicole'), GuestAgent(name='Brad')]
manager = Simulation(guests)

# Simulate the auction for a maximum of 15 rounds
for i in range(15):
    # Process guest responses
    # Process auctioneer's response
    # Check for auction completion
```

## Notes
- The simulation demonstrates basic auction dynamics with AI agents.
- The project can be expanded by adding more complex bidding strategies or different auction types.
- Ensure that the OpenAI API usage complies with OpenAI's use case policies.

