# ⚓ Kelvin The Diver (v6.4)

**Kelvin The Diver** is a browser-based underwater exploration and survival game built entirely in vanilla JavaScript and HTML5 Canvas. Dive into the abyss, manage your oxygen, battle deep-sea creatures, and upgrade your gear to face the Leviathan.

## 🌊 Game Overview

You play as Kelvin, a diver seeking fortune in the deep. Your goal is to harpoon fish, collect treasure, and return to the surface to sell your catch. Use your earnings to upgrade your equipment, allowing you to dive deeper into the dark zones where more dangerous creatures—and valuable treasures—lurk.

### Key Features

* **Procedural Terrain:** The seabed is generated procedurally every time the game initializes.

* **Day/Night Lighting:** Dynamic lighting system that gets darker as you descend; includes a flashlight mechanic.

* **Shop & Upgrade System:** Buy upgrades for your Harpoon, Oxygen Tank, and Cargo Suit.

* **Physics-based Movement:** Momentum, water drag, gravity, and buoyancy mechanics.

* **Boss Battle:** A scripted encounter with the "Leviathan" at extreme depths (~8000m).

* **Mobile Support:** Fully responsive with on-screen virtual joysticks for touch devices.

## 🎮 How to Play

### Controls

| Action | Desktop (Keyboard/Mouse) | Mobile (Touch) |

| **Move** | `W`, `A`, `S`, `D` | Left Virtual Joystick |

| **Aim** | Mouse Cursor | Right Virtual Joystick |

| **Shoot** | Left Click | Drag Right Joystick & Release |

| **Boost** | `Spacebar` | "BOOST" Button |

### Core Loop

1.  **Dive:** Descend from the boat. Watch your Oxygen (O2) bar.

2.  **Hunt:** Aim and fire your harpoon at fish.

    * **Hooking:** If you reduce a fish's HP to 0 and have cargo space, you catch it.

    * **Culling:** If your cargo is full, reducing a fish to 0 HP "eliminates" it (no loot).

3.  **Loot:** Collect floating chests and avoid sea mines.

4.  **Return:** Swim back to the surface (water level) to refill O2 and open the Shop.

## 🛒 The Dry Dock (Shop)

When you surface near your boat, the shop opens automatically.

* **Sell All:** Exchange your caught fish for cash.

* **Harpoon Tech:** Increases damage. Level 5+ unlocks "Trident" mode (3 projectiles).

* **O2 Tank:** Increases maximum oxygen capacity.

* **Cargo Suit:** Increases maximum weight capacity ($Kg$).

## 🐡 Bestiary & Hazards

* **Clowny & Bluefin:** Passive, shallow water fish.

* **Puffer:** Inflates spikes. Don't touch!

* **Jelly:** Aggressive, glows in the dark. Found in the twilight zone.

* **Stingray:** Large, fast, passive unless provoked.

* **Angler:** Deep sea predator with a lure. Very aggressive.

* **Mines:** Stationary explosives dealing massive damage and O2 loss.

* **The Leviathan:** The guardian of the bottom. Good luck.

## 🛠️ Technical Details

This game is contained entirely within a single `index.html` file. It requires no external assets, libraries, or build steps.

### Installation / Running

1.  Download the `index.html` file.

2.  Open it in any modern web browser (Chrome, Firefox, Safari, Edge).

3.  Enjoy!

### Architecture

* **Rendering:** Uses HTML5 `<canvas>` (2D Context) for all graphics. No sprite sheets are used; all visuals (fish, boat, particles) are drawn using canvas primitives (`ctx.arc`, `ctx.bezierCurveTo`, etc.) or pattern generation.

* **Game Loop:** Uses `requestAnimationFrame` for a smooth 60FPS loop handling `update()` and `draw()`.

* **State Management:** Simple state machine handling `playing`, `shop`, and `dead` states.

* **Lighting Engine:** Uses a secondary `maskCanvas` with `globalCompositeOperation = 'destination-out'` to create the flashlight tunnel effect and darkness overlays.

### v6.3 Changelog ("The Culling Update")

* **Inventory Logic:** Fixed an issue where hooking a fish with a full inventory caused bugs. Now, if the inventory is full, the fish is destroyed upon 0 HP.


## 📄 License

This project is provided as-is. Feel free to modify, learn from, or expand upon the code.


 
