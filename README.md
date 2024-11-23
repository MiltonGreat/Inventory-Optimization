# Warehouse Inventory Optimization using Reinforcement Learning

## Project Overview

This project aims to create a reinforcement learning (RL) model to optimize stock levels for a warehouse. The objective is to balance carrying costs and out-of-stock risks by training an RL agent to interact with a warehouse environment and make optimal stock-level decisions.

The agent is trained using a Deep Q-Network (DQN) to manage inventory by adjusting stock levels based on demand, penalties for stockouts, and carrying costs. The environment simulates the dynamics of a warehouse inventory system.

## Dataset

The dataset used in this project contains historical sales data from a warehouse. The key features of the dataset include:

- Order Quantity: The quantity of products ordered.
- Unit Cost: The cost per unit.
- Unit Price: The selling price per unit.
- OrderDate and DeliveryDate: The dates of the orders and deliveries.
- _ProductID: Unique identifier for products.

The data undergoes preprocessing, which includes:

- Cleaning price columns by removing currency symbols.
- Converting dates into a datetime format.
- Calculating additional features like LeadTime, TotalRevenue, and TotalCost.

### Key Features:

- `age`: Age of the customer.
- `job`: Type of job.
- `balance`: Customer's account balance.
- `duration`: Duration of the last contact with the customer.
- `campaign`: Number of contacts performed during the campaign.
- `previous`: Number of contacts before the campaign.
- `loan`: Whether the customer has a loan.

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.

## Training the RL Model

1. Environment: The WarehouseEnv class simulates the warehouse environment. It includes:
- state: The current stock levels of products.
- actions: The actions available to the agent (-1 to reduce stock, 0 to maintain stock, and 1 to increase stock).
- reward: Calculated based on stock levels, carrying costs, and stockout penalties.

2. Agent: The RL agent is implemented using a Deep Q-Network (DQN). It interacts with the environment by choosing actions and learning from the rewards it receives.

3. Training: The model is trained using the DQN algorithm, where the agent interacts with the environment, updates its Q-values, and learns to balance stock levels optimally.


## Key Results

- Training Performance: The agent's performance during training can be tracked by the total rewards received at the end of each episode. Example output:

- Test Performance: After training, the agent's performance during a test run showed a total reward of -2030285242.96, which indicates the penalties and costs incurred.

## Source:

https://www.kaggle.com/datasets/dorothyjoel/us-regional-sales
