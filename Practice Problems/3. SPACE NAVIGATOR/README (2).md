# Starfleet Navigator - Space Exploration Management

## Overview
Welcome to **Starfleet Navigator**, an advanced-level Django project where you will design a system to manage starships, celestial bodies, and exploration missions. This project involves complex relationships between models, challenging queries, and comprehensive testing.

---

## Project Structure

### Models

#### **CelestialBody**
- **Fields**:
  - `name`: The name of the celestial body.
  - `type`: The type of celestial body (e.g., Planet, Star, Asteroid).
  - `distance_from_earth`: The distance from Earth in light-years.

#### **Starship**
- **Fields**:
  - `name`: The name of the starship.
  - `model`: The model of the starship.
  - `crew_capacity`: The number of crew members the starship can hold.
  - `current_mission`: A `ForeignKey` to the `Mission` model, optional.

#### **Mission**
- **Fields**:
  - `name`: The name of the mission.
  - `objective`: The primary objective of the mission.
  - `reward`: The reward for completing the mission.
  - `celestial_body`: A `ForeignKey` to the `CelestialBody` model.

---

## Functions

### Creation Functions

#### **create_celestial_body(name, type, distance_from_earth)**
- **Description**: Creates and returns a new `CelestialBody` instance.
- **Parameters**:
  - `name` (str): The name of the celestial body.
  - `type` (str): The type of celestial body.
  - `distance_from_earth` (float): The distance of the celestial body from Earth in light-years.
- **Returns**: `CelestialBody` instance.

#### **create_starship(name, model, crew_capacity)**
- **Description**: Creates and returns a new `Starship` instance.
- **Parameters**:
  - `name` (str): The name of the starship.
  - `model` (str): The model of the starship.
  - `crew_capacity` (int): The crew capacity of the starship.
- **Returns**: `Starship` instance.

#### **create_mission(name, objective, reward, celestial_body)**
- **Description**: Creates and returns a new `Mission` instance.
- **Parameters**:
  - `name` (str): The name of the mission.
  - `objective` (str): The primary objective of the mission.
  - `reward` (int): The reward for completing the mission.
  - `celestial_body` (CelestialBody): The celestial body associated with the mission.
- **Returns**: `Mission` instance.

### Query Functions

#### **assign_mission(starship, mission)**
- **Description**: Assigns a `Mission` to a `Starship` and saves the changes.
- **Parameters**:
  - `starship` (Starship): The starship to be assigned a mission.
  - `mission` (Mission): The mission to be assigned.
- **Returns**: Updated `Starship` instance.

#### **list_missions_by_objective(objective)**
- **Description**: Returns all `Mission` instances with the specified objective.
- **Parameters**:
  - `objective` (str): The objective to filter missions by.
- **Returns**: QuerySet of `Mission` instances.

#### **nearest_celestial_body()**
- **Description**: Returns the `CelestialBody` closest to Earth.
- **Returns**: `CelestialBody` instance.

#### **mission_rewards_summary(celestial_body)**
- **Description**: Returns the total rewards for all missions related to the specified celestial body.
- **Parameters**:
  - `celestial_body` (CelestialBody): The celestial body to calculate rewards for.
- **Returns**: Integer value representing the total rewards.

---

## Testing

Write comprehensive tests for the following:

1. **`create_celestial_body`**:
   - Verify a `CelestialBody` is created correctly with the specified attributes.
   - Handle edge cases like missing or invalid input.

2. **`create_starship`**:
   - Ensure a `Starship` is created with the correct attributes.
   - Test edge cases like invalid `crew_capacity` values (e.g., negative numbers).

3. **`create_mission`**:
   - Confirm a `Mission` is created correctly with the specified attributes.
   - Verify the `ForeignKey` relationship to the `CelestialBody` model.

4. **`assign_mission`**:
   - Ensure the function correctly assigns a mission to a starship.
   - Handle edge cases, such as assigning a mission that doesn’t exist.

5. **`list_missions_by_objective`**:
   - Verify all missions with the specified objective are returned.
   - Test behavior for objectives with no missions.

6. **`nearest_celestial_body`**:
   - Confirm the function correctly identifies the celestial body closest to Earth.
   - Handle edge cases, such as no celestial bodies in the database.

7. **`mission_rewards_summary`**:
   - Ensure the function calculates the total rewards correctly.
   - Test behavior for celestial bodies with no missions.

---

## Additional Tips

- Use Django’s `TestCase` to write your tests.
- Test edge cases thoroughly, such as missing or invalid input.
- Validate relationships between models to ensure data integrity.

