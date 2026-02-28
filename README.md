# AgentsVille Trip Planner

A multi-stage AI assistant that generates and refines personalized travel itineraries for the fictional city of AgentsVille.

## Overview

The system uses LLM-powered agents to:

- **Understand** traveler preferences — duration, interests, budget, and constraints
- **Plan** a detailed, day-by-day itinerary as structured JSON (validated via Pydantic)
- **Evaluate & Refine** the plan using a ReAct (Think → Act → Observe) agent loop with tool access

## Key Components

| Component | Description |
|---|---|
| `VacationInfo` | Pydantic model capturing traveler preferences |
| `ItineraryAgent` | Generates an initial structured itinerary via a single LLM call |
| `Evaluation Suite` | Validates budget accuracy, activity availability, weather suitability, and more |
| `ItineraryRevisionAgent` | ReAct agent that iteratively refines the plan using tools and evaluation feedback |

## Tools Available to the Revision Agent

- **calculator_tool** — accurate cost calculations
- **get_activities_by_date_tool** — retrieve available activities for a given date
- **run_evals_tool** — evaluate the itinerary against quality criteria
- **final_answer_tool** — signal completion and return the final itinerary

## Tech Stack

- Python, Jupyter Notebook
- OpenAI API (LLM)
- Pydantic (data validation)

## Files

- `project_starter.ipynb` — main notebook with the implementation
- `project_lib.py` — helper functions, models, and simulated APIs
