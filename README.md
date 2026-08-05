# Multi-Agent Adversarial Fact-Checker


LangGraph is an orchestration framework.

                 User

                  │

                  ▼

          Claim Parser Agent

                  │

                  ▼

        Task Orchestrator Agent

          │                │

          ▼                ▼

   Defense Agent     Prosecutor Agent

          │                │

          └──────┬─────────┘

                 ▼

        Evidence Aggregator

                 ▼

        Source Ranking Agent

                 ▼

           Judge Agent

                 ▼

     Explanation Generator

                 ▼

       Structured JSON Report

       

#### Defense Agent:

System prompt:
You are a defense lawyer.
Your job is to find evidence supporting the claim.
Never accept the claim without evidence.
Search official sources first.

#### Prosecutor:
You are a skeptical investigator.
Your job is to find evidence against the claim.
Look for contradictions.

Same model.
Since the prompt are different.... you will see different behavior


Adding a Claim Parser at the beginning of the frame work

User: "I heard Tesla lost 50% of its value because Elon Musk left in March 2026 and analysts confirmed bankruptcy."

This is actually multiple claims.

A human researcher breaks it down:
Claim 1: Elon Musk left Tesla
Claim 2: Tesla lost 50% value
Claim 3: Analysts confirmed bankruptcy

Different evidence is needed for each. Now agents receive cleaner information.
