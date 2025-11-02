dPoll Project Roadmap

This document outlines the development plan for dPoll, a simple decentralized polling application built on Soroban. This plan is designed to be achievable within a hackathon timeframe by modifying existing examples from the Soroban documentation repository.

Project Goal

To build a smart contract that stores counters for two options ("Option A" and "Option B") and a simple webpage that lets users click buttons to vote, displaying the results dynamically.

Phase 1: Environment Setup & Foundation

Objective

Prepare the local development environment for Soroban smart contract and frontend development.

Key Tasks

Read 00. Setup.md and docs/getting-started/environment-setup.md.

Install all "Prerequisites" and tools as listed in the documentation.

Ensure the Soroban CLI is working and you can compile and run the example contracts.

Relevant Docs

00. Setup.md

docs/getting-started/environment-setup.md

Phase 2: The Smart Contract (Backend Logic)

Objective

Create the dPoll smart contract that manages and stores the vote counts. This will be achieved by modifying the increment/ example.

Base Example

increment/

Key Tasks

Understand State: Read docs/smart-contracts/contract-state.md to understand how to store data.

Adapt State: Modify the contract's state to store two counters (e.g., VOTES_A, VOTES_B) instead of one.

Modify Functions:

Rename increment() to vote_a().

Update vote_a() to only increment the counter for "Option A".

Create New Functions:

Create vote_b(): This function will increment the counter for "Option B".

Create get_votes_a(): A "getter" function that returns the current count for "Option A".

Create get_votes_b(): A "getter" function that returns the current count for "Option B".

Test Contract:

Follow docs/smart-contracts/testing-contracts.md.

Write and run tests to ensure vote_a, vote_b, and the getter functions all work as expected.

Deploy Locally: Deploy the finalized dPoll contract to your local network.

Relevant Docs

docs/smart-contracts/contract-state.md

docs/smart-contracts/testing-contracts.md

Phase 3: The Frontend (Voting Booth UI)

Objective

Build a simple webpage that allows users to interact with the deployed dPoll smart contract. This will be achieved by modifying the frontend_hello_world/ example.

Base Example

frontend_hello_world/

Key Tasks

Connect Contract:

Read docs/frontend/connecting-to-contracts.md.

Update the frontend code to use your new dPoll contract ID.

Update UI (HTML):

Remove the "Hello World" button and related text.

Add two new buttons: "Vote for Option A" and "Vote for Option B".

Add a section to display results (e.g., "Current Results:").

Update Logic (JavaScript):

Read docs/frontend/user-interaction.md.

Connect the "Vote for Option A" button to call the vote_a() function on your smart contract.

Connect the "Vote for Option B" button to call the vote_b() function on your smart contract.

Display Results:

Write JavaScript that periodically calls the get_votes_a() and get_votes_b() functions.

Display the returned vote counts on the webpage, updating them after a vote is cast.

Relevant Docs

docs/frontend/connecting-to-contracts.md

docs/frontend/user-interaction.md# dpoll-hackathon
a dpoll smart contract and web frontend for simple voting application on soroban 
