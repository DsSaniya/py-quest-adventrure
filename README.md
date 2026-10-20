# py-quest-adventrure
import random
import time

# --- Player State - This is what you show on resume ---
player = {
    "health": 100,
    "score": 0,
    "inventory": []
}

def show_status():
    print(f"\n❤️ Health: {player['health']} | ⭐ Score: {player['score']} | 🎒 Inventory: {player['inventory']}")

def random_event():
    events = [
        {"text": "You found a healing potion!", "health": 20, "score": 10, "item": "Potion"},
        {"text": "A wild monster attacked you!", "health": -30, "score": 5, "item": None},
        {"text": "You discovered a hidden treasure chest!", "health": 0, "score": 30, "item": "Gold Coin"},
        {"text": "You fell into a trap!", "health": -15, "score": -5, "item": None}
    ]
    return random.choice(events)

def main():
    print("=== PY-QUEST ADVENTURE ===")
    print("You wake up in a mysterious dungeon. Find the exit!")
    print("Commands: explore, inventory, quit")

    while player["health"] > 0:
        show_status()
        action = input("\nWhat do you do? > ").lower()

        if action == "quit":
            print(f"Game Over! Final Score: {player['score']}")
            break
        
        elif action == "inventory":
            print(f"Your bag contains: {player['inventory']}")
