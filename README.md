# Inkfinity Platform

## Purpose
Inkfinity Platform is the foundation for Inkfinity’s AI-powered onboarding and hub creation system.

The goal is to allow a business to:
• Submit a simple onboarding form  
• Automatically generate a branded digital hub (links, buttons, QR destinations)  
• Reduce setup time to minutes, not days  

This repository will evolve into the core logic that powers:
• AI-assisted onboarding
• Smart link suggestions
• Scalable hub generation

## Status
🚧 Early stage – active build  
Initial focus: onboarding flow, data structure, and automation logic.

## Owner
Inkfinity Ltd  
## Output

Onboarding responses are processed using mapping rules defined in:

/hub/mapping.json

A completed onboarding submission is transformed into a Hub object
as defined in:

/hub/model.json

See a full example:

• Input: /hub/example_onboarding_submission.json  
• Output: /hub/example_output_hub.json
