# Use Cases

This directory contains use case scenarios for Operational Design Domain (ODD) testing and validation. The use cases are defined to test various autonomous driving system behaviors in specific operational conditions.

## Overview

Use cases in this directory follow a structured format based on the [Gherkin](https://cucumber.io/docs/gherkin/) syntax, specifically using [Markdown with Gherkin (MDG)](https://github.com/cucumber/gherkin/blob/main/MARKDOWN_WITH_GHERKIN.md) format, providing clear and testable scenarios for autonomous vehicle validation.

## File Structure

- `UC-[TYPE]-[ID]-[VERSION].feature.md`: Use case definition files
- `UC-[TYPE]-[ID]-[VERSION].png`: Associated scenario diagrams

Where:

- `TYPE`: Category of use case (e.g., NTR for No Traffic Rules scenarios)
- `ID`: Unique identifier within the category
- `VERSION`: Version number of the use case

## Scenario Writing Guidelines

### Keyword Usage

Follow the Gherkin syntax with specific semantic meanings:

- **Given**: Describe the initial scene of the scenario, including:
  - Road characteristics required for the scenario to work
  - Initial status of all actors
  - Any variations that must be covered by test scenarios

- **When**: Describe behaviors of the scene and other actors surrounding Ego

- **Then**: Describe the Ego reaction and expected outcomes

### Actor Naming

Use predefined actor names with consistent conventions:

- **Primary actors**: `Ego`, `Car`, `Pedestrian`, `Bicycle`, `Motorbike`, `Bus`, `Truck`, `Animal`
- **Uniqueness**: `Ego` must be unique; other actors use suffix `{0...n}` for identification
- **Examples**: `Car0`, `Car1`, `Pedestrian0`, `Truck2`

### Parameter Naming

Parameters must follow `snake_case` convention with standardized abbreviations:

#### Actor State Parameters

- Position: `s`
- Velocity: `v`
- Acceleration: `a`
- Jerk: `j`

#### General Parameters

- Distance: `d`
- Directions:
  - Longitudinal: `x`
  - Lateral: `y`
  - Euclidean: `e`

#### Value Types

- Initial: `i`
- Minimum: `min`
- Maximum: `max`
- Target: `tar`
- Front: `f`
- Rear: `r`

#### Parameter Construction Rules

- Abbreviations come first in parameter names
- Abbreviations can be concatenated
- Actor state parameters must reference the target actor
- Example: `vxi_car0` = car0_initial_longitudinal_velocity
