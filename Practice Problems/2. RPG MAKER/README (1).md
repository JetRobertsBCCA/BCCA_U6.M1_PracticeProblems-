# Character Keeper - RPG Management System

## Overview
Welcome to **Character Keeper**, an intermediate-level Django project where you will build a system to manage RPG characters, their abilities, and their equipment. This project emphasizes database relationships and querying while giving you hands-on practice with Django.

---

## Project Structure

### Models

#### **Character**
- **Fields**:
  - `name`: The name of the character.
  - `class_type`: The class of the character (e.g., Warrior, Mage, Rogue).
  - `level`: The character's current level.
  - `health_points`: The character's health points.

#### **Ability**
- **Fields**:
  - `name`: The name of the ability.
  - `power_level`: The power level of the ability.
  - `character`: A `ForeignKey` to the `Character` model.

#### **Equipment**
- **Fields**:
  - `name`: The name of the equipment.
  - `equipment_type`: The type of equipment (e.g., Weapon, Armor).
  - `damage`: The damage value (for weapons) or protection value (for armor).
  - `character`: A `ForeignKey` to the `Character` model.

---

## Functions

### Creation Functions

#### **create_character(name, class_type, level, health_points)**
- **Description**: Creates and returns a new `Character` instance.
- **Parameters**:
  - `name` (str): The name of the character.
  - `class_type` (str): The character’s class.
  - `level` (int): The character’s level.
  - `health_points` (int): The character’s health points.
- **Returns**: `Character` instance.

#### **create_ability(name, power_level, character)**
- **Description**: Creates and returns a new `Ability` instance.
- **Parameters**:
  - `name` (str): The name of the ability.
  - `power_level` (int): The power level of the ability.
  - `character` (Character): The `Character` instance associated with the ability.
- **Returns**: `Ability` instance.

#### **create_equipment(name, equipment_type, value, character)**
- **Description**: Creates and returns a new `Equipment` instance.
- **Parameters**:
  - `name` (str): The name of the equipment.
  - `equipment_type` (str): The type of equipment.
  - `value` (int): The damage (weapons) or protection (armor).
  - `character` (Character): The `Character` instance associated with the equipment.
- **Returns**: `Equipment` instance.

### Query Functions

#### **list_abilities(character)**
- **Description**: Returns all `Ability` instances for the specified character.
- **Parameters**:
  - `character` (Character): The character whose abilities are being queried.
- **Returns**: QuerySet of `Ability` instances.

#### **highest_power_ability(character)**
- **Description**: Returns the `Ability` with the highest power level for the specified character.
- **Parameters**:
  - `character` (Character): The character whose abilities are being queried.
- **Returns**: `Ability` instance.

#### **character_equipment_summary(character)**
- **Description**: Returns a summary of the equipment (names and types) associated with the character.
- **Parameters**:
  - `character` (Character): The character whose equipment is being summarized.
- **Returns**: List of tuples (equipment name, equipment type).

---

## Testing

Write comprehensive tests for the following:

1. **`create_character`**:
   - Verify a `Character` is created correctly with the specified attributes.
   - Handle edge cases like missing or invalid input.

2. **`create_ability`**:
   - Confirm an `Ability` is created correctly and associated with the correct character.
   - Test invalid `power_level` values (e.g., negative numbers).

3. **`create_equipment`**:
   - Ensure `Equipment` is created correctly and associated with the correct character.
   - Test invalid `equipment_type` values (e.g., unsupported types).

4. **`list_abilities`**:
   - Confirm all abilities for a character are returned.
   - Test behavior for characters with no abilities.

5. **`highest_power_ability`**:
   - Verify the function correctly identifies the highest power ability.
   - Handle edge cases, such as characters with no abilities.

6. **`character_equipment_summary`**:
   - Ensure the function lists all equipment for a character.
   - Test behavior for characters with no equipment.

---

## Additional Tips

- Use Django’s `TestCase` to write your tests.
- Test edge cases thoroughly, such as missing or invalid input.
- Ensure relationships between models are working as expected.



