# Use Cases

This directory contains use case scenarios for Operational Design Domain (ODD) testing and validation. The use cases are defined to test various autonomous driving system behaviors in specific operational conditions.

# Overview

Use cases in this directory follow a structured format based on the [Gherkin](https://cucumber.io/docs/gherkin/) syntax, specifically using [Markdown with Gherkin (MDG)](https://github.com/cucumber/gherkin/blob/main/MARKDOWN_WITH_GHERKIN.md) format, providing clear and testable scenarios for autonomous vehicle validation.

# File Structure

- `UC-[TYPE]-[ID]-[SUB ID].feature.md`: Use case definition files
- `UC-[TYPE]-[ID]-[SUB ID].png`: Associated scenario diagrams

Where:

- `TYPE`: Category of use case (e.g., NTR for No Traffic Rules scenarios)
- `ID`: Unique identifier within the category
- `SUB ID`: Sub-identifier for more granular use case differentiation

# Scenario Writing Guidelines

## Language

- Scenarios must be written in English
- Scenarios must be written in third person
- Scenarios must be written in either simple present or present continuous 
- Scenarios must be written in full subject-predicate sentences
- Scenarios must be written in positive assertions

**Examples**:
- OK) Ego starts driving (simple present, third person)
- OK) Ego continues driving (positive)
- NG) You start driving (second person plural)
- NG) Ego will start driving (future tense)
- NG) Ego does not stop (negative)

## Feature and Scenario Descriptions

When writing use cases, include clear descriptions for Features and Scenarios:

- **Feature Description**: Explain **Why** - the rationale and necessity for the feature being tested
- **Scenario Description**: Explain **What** - specifically what behavior or condition is being tested

## Keyword Usage

Follow the Gherkin syntax with specific semantic meanings:

- **Given**: Must describe the initial scene of the scenario, including:
  - Road characteristics required for the scenario to work
  - Initial status of all actors
  - Any variations that must be covered by test scenarios
  Note: If all scenarios within the `Feature` or `Rule` share common `Given` steps, extract them into a `Background` section.

- **When**: Must describe behaviors of the scene and other actors surrounding Ego, including:
  - State changes of scenario elements other than Ego
  - Actions of scenario elements other than Ego
  - Relative state changes or actions of Ego with other scenario elements[^1]

- **Then**: Must describe the Ego's reaction to the preceding `When` statement, including:
  - Ego actions
  - Ego measurable state changes
  - Relative state changes or actions of Ego with other scenario elements[^1]

- **And/But**: May be used to provide additional information to the keyword in the preceding line. No omissions are allowed, even if the information can be implied by the preceding statement.

[^1]:  Relative state changes or actions that involve Ego and at least one other scenario element can be described in both `When` or `Then` sections, depending on whether it acts as a trigger to an Ego behavior, or as its response.

## Traffic Participant Naming

Actors that represent traffic participants must use a predefined name that matches its type.

- **Traffic participant names**: `Ego`, `Car`, `Pedestrian`, `Bicycle`, `Motorbike`, `Bus`, `Truck`, `Animal`

- **Uniqueness**: 
  - `Ego` must be unique.
  - Other actors must use an incremental suffix to provide a unique identification between actors of the same type:
    - The suffix must always be present, even if a single actor of that type exists (excluding `Ego`).
    - The suffix must start at 0 (`{0...n}`), incrementing once for every actor of the given type that already exists in the scenario.
    - The suffix must be directly appended to the actor's name, without a dash (`-`) or underscore (`_`).

**Examples**: 
- OK) `Car0`, `Car1`
- OK) `Pedestrian0`
- OK) `Truck0`
- NG) `Ego0` (Ego should not take a suffix)
- NG) `ego` (the name should follow the capitalization in the predefined names)
- NG) `Car0`, `Car2` (without a `Car1`)

## Parameter Naming

- Parameter names must follow the `snake_case` convention.
- Parameters that describe the state of one or more actors must explicitly include the referenced actors' names, in lower case and separated by underscores (`_`).
- The parameter names must be chosen so that their intended purpose is clear and unambiguous.
- Only a predefined set of parameter name abbreviations shall be used. Except these, all parameters names shall be written in their full extent.
  - When present, abbreviations must come first in parameter names.
  - Additional context may be provided to the abbreviated state parameter following the order: [Actor state][Direction][Value type]
  - The list of parameters that accept abbreviation are described in the sections below.

### Actor State Parameters

- Position: `s`
- Velocity: `v`
- Acceleration: `a`
- Jerk: `j`

### Actor Relative State Parameters

- Distance: `d`
- Relative velocity: `vrel`

### Additional Context: Directions

- Longitudinal: `x`
- Lateral: `y`
- Euclidean: `e`

### Additional Context: Value Types

- Initial: `i`
- Minimum: `min`
- Maximum: `max`

**Examples**: 
- OK) `vxi_car0` = car0_initial_longitudinal_velocity
- OK) `vrelx_car0_ego` = car0_ego_relative_longitudinal_velocity
- OK) `wind_direction` = wind_direction
- NG) `vrelx_car0` (missing the second actor referenced by the relative parameter)
- NG) `ego_vy` (abbreviated part is not the first component of the parameter name)

## Event Timings

When describing two or more events’ temporal relationships, [Allen's Interval Algebra](https://en.wikipedia.org/wiki/Allen%27s_interval_algebra) is commonly used.

Due to the high abstraction nature of the functional scenarios that will be described with the current format, it was deemed unnecessary (at least for now) to define the timing of events in such a strict manner. Therefore, only the concepts of `sequential` vs `parallel` are adopted.

- `Sequential` covers: before/after/meets/is met by
- `Parallel` covers: overlaps/is overlapped by/during/contains/starts/is started by/finishes/is finished by/equal

The approach for describing such relationships in Gherkin also differs depending on the keywords involved in both events. Thus, the convention is illustrated in the table below, which illustrates all 4 possible combinations:

| Temporal Relationship | When → And/But | When → Then | Then → And/But | Then → When |
|-----------------------|-------------------------------|---------------------------|-----------------------|---------------------------|
| Sequential            | When [EVENT A]<br>And `later` [EVENT B] | When [EVENT A]<br>Then `later` [EVENT B] | Then [EVENT A]<br>And `later` [EVENT B] | Then [EVENT A]<br>When [EVENT B] `after` [EVENT A] |
| Parallel              | When [EVENT A]<br>And `at the same time` [EVENT B] | When [EVENT A]<br>Then `at the same time` [EVENT B] | Then [EVENT A]<br>And `at the same time` [EVENT B] | Then [EVENT A]<br> When [EVENT B] `during` [EVENT A] |

- To ensure that the representation above works, multiple events chained with the “And” and “But” keywords must be ordered appropriately:
  1. Events happening parallel to each other must be grouped together.
  2. Events groups must be sorted by earliest occurrence timing.
  3. Only the first sentence of each event group shall use the representation phrasing described in the table above, to represent the timing relationship between the two groups.
- If the expressions specified on the table above are absent, that implies that the timing between the two events is not defined in a strict manner.
- This framework allows for the loose differentiation between events that must happen without any overlap vs those that allow any level of overlap. 
- If the specific time gap between the events is important for the criticality of the scenario, it should be defined as a scenario parameter.

## Continuously Met Conditions

When describing driving scenarios, there may be times when it is desirable to specify a specific condition that Ego must obey from the start of the scenario until its end.
Gherkin does not provide a built-in approach for defining these types of conditions, so it must be handled in a custom ruleset.

If the number of `When`/`Then` steps is low (~2), then it is possible to simply repeat the condition in all `Then` sections. The problem is when there is a large number of steps, making the repetitions take increasingly more space and degrading the scenario's readability. To handle these cases, the following **optional** approach can be adopted:
- List the continuously met conditions only on the last `Then` keyword of the scenario.
- Each condition must be described in a separate statement.
- At the end of each condition, append "at all times" to clearly state the intended meaning.

**Example**:
- OK)
  > When Car0 drives past Ego<br>
  > Then Ego drives straight at the same speed<br>
  > And Ego drives with no collisions<br>
  > When Car0 cuts in ahead of Ego<br>
  > Then Ego slows down<br>
  > And Ego drives with no collisions

- OK)
  > When Car0 drives past Ego<br>
  > Then Ego drives straight at the same speed<br>
  > When Car0 cuts in ahead of Ego<br>
  > Then Ego slows down<br>
  > And Ego drives with no collisions at all times<br>

