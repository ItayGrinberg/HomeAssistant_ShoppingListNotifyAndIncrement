# HomeAssistant_ShoppingListCounter

This repository contains a **Home Assistant automation blueprint** that increments a counter when a shopping list item is marked as purchased, with a user prompt to specify the quantity purchased.

---

## 📋 Description

This automation helps manage and track item purchases in your Home Assistant setup. When an item is marked as purchased in a shopping list entity (a todo entity), this automation:

✅ Prompts the user (via mobile notification) to select how many items were purchased.  
✅ Supports quick-select options and manual input.  
✅ Increments a counter with the selected quantity.  
✅ Allows the user to specify a delay before the notification is sent.  
✅ Allows a configurable timeout period for waiting for user input.
Check out this related automation that lets you easily add items to your shopping list with user-selected triggers: [Related Blueprints](#-related-blueprints)

---

## 🗂️ Table of Contents

- [Description](#-description)
- [Features](#️-features)
- [Blueprint Inputs](#-blueprint-inputs)
- [How to Use](#-how-to-use)
- [Example Use Case](#-example-use-case)
- [Related Blueprints](#-related-blueprints)
- [Requirements](#-requirements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🛠️ Features

- **Shopping List Monitoring**: Automatically detects when an item is marked as purchased.
- **User Prompt**: Sends a mobile notification prompting the user for the quantity purchased.
- **Quick-Select Buttons**: Offers predefined quick-select options (e.g. +1, +2).
- **Manual Input**: Allows users to manually input the quantity via text reply.
- **Counter Update**: Automatically increments a Home Assistant counter with the purchased quantity.
- **Optional Delay**: Adds a delay (in minutes) before sending the notification.
- **Customizable Timeout**: Allows configuration of how long to wait for a user response before dismissing the notification.

---

## 📦 Blueprint Inputs

| Input | Description |
|-------|-------------|
| `counter_target` | The counter entity to increment. |
| `current_state_boolean` | Helper input_boolean that tracks the current item state. |
| `purchased_item` | The shopping list item to monitor for purchase. |
| `shopping_list_entity` | The shopping list (todo entity) to monitor. |
| `number_1` | Quick-select option 1 (number). |
| `number_2` | Quick-select option 2 (number). |
| `notify_target` | The mobile device to send the notification to. |
| `timeout_hours` | Timeout duration in hours to wait for the user's response. |
| `delay_before_notify` | Optional delay (in minutes) before sending the notification. |

---

## 🚀 How to Use

1. **Import the Blueprint**  
   Download or copy the `IncrementCounterOnShoppingListItemPurchase.yaml` from this repository into your Home Assistant `/config/blueprints/automation` folder or click the following link:

   [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FItayGrinberg%2FHomeAssistant_ShoppingListNotifyAndIncrement%2Fblob%2Fmain%2FIncrementCounterOnShoppingListItemPurchase.yaml)
   

3. **Configure the Automation**  
   - Select your counter entity.
   - Select (or create) the item state helper (input_boolean). 
   - Enter the name of the purchased item.
   - Select the shopping list entity (must be a `todo` entity).
   - Set quick-select amounts (optional).
   - Select the mobile device for notifications.
   - Set the timeout in hours for the user response.
   - (Optional) Set a delay (in minutes) before sending the notification.

4. **Activate the Automation**  
   Enable the automation in Home Assistant.

---

## 🔧 Example Use Case

- **Scenario**: You buy milk from the grocery store and mark it as purchased in your shopping list app.
- **What Happens**:  
  - The automation detects the purchase.
  - After the optional delay, your mobile device receives a prompt: "How many milk did you buy?"
  - You can tap a quick-select button (+1, +2) or reply with another number.
  - The automation increments the milk stock counter accordingly.

---

## 🔗 Related Blueprints

This blueprint complements another automation blueprint designed to **add items to the shopping list** from Home Assistant:

👉 [HomeAssistant_AddItemToShoppingListBlueprint](https://github.com/ItayGrinberg/HomeAssistant_AddItemToShoppingListBlueprint)

Use both together for a seamless shopping list management experience.

---

## 📝 Requirements

- Home Assistant 2024.4 or later (for robust blueprint support)
- A shopping list integration (must be a `todo` entity)
- A mobile device set up with the `mobile_app` integration
- A counter entity in Home Assistant (can be created via the blueprint setup)
- An input_boolean helper to track the item's purchase state (can be created via the blueprint setup)

---

## 🤝 Contributing

Feel free to open issues or pull requests to improve this blueprint! Suggestions and improvements are always welcome.

---

## 📜 License

This project is licensed under the MIT License.
