# PlutoBlocks Guide Book

This repository contains the interactive Guide Book for **PlutoBlocks V4**, a block-based programming interface for programming Pluto Platform STM32-based drones. The guide book provides documentation, functions, and example project ideas for all the available blocks.

---

## 📚 Blocks Covered

The guide book covers all essential and advanced blocks categorized under the following sections:

| Section | Description & Blocks Covered |
| :--- | :--- |
| **1. Core Blocks** | Setup and loop structures: `Select Receiver Mode`, `On Start`, `Pluto Loop`, and `On Stop`. |
| **2. LED** | Controlling red, green, and blue LEDs. |
| **3. Create Function** | Grouping blocks into custom reusable routines and embedding custom C++ logic. |
| **4. Timer** | Starting millisecond countdown intervals (`Set Timer`), checking status (`Timer Done?`), and reading elapsed values (`Get Timer`). |
| **5. Peripheral** | Interface with external hardware: `Read ADC`, `Digital Write/Read`, `Servo Control`, and `PWM Output`. |
| **6. Command** | Basic flight triggers: Takeoff, Landing, Arming, Disarming (Kill-Switch), and 360-degree aerial backflips. |
| **7. Motor** | Direct speed control blocks for individual motors (`M1` to `M6`). |
| **8. Remote Control** | Reading and overriding real-time RC transmitter stick inputs (Roll, Pitch, Throttle, Yaw). |
| **9. Sensor** | Reading onboard flight sensors: Accelerometer, Gyroscope, Magnetometer, Barometer, and Battery Health. |
| **10. Current State** | Retrieving live flight telemetry parameters: Roll, Pitch, Yaw, Height, and App Heading. |
| **11. Desired State** | Setting flight target coordinates: Target Roll, Target Pitch, Target Yaw, and Target Height. |
| **12. Flight Mode** | Checking active flight modes: Headfree Mode and Throttle Mode. |
| **13. Flight Status** | Monitoring critical safety and operational flags: Armed status, OK to Arm check, Signal Loss, Crash detection, and Low Battery warnings. |
| **14. Console** | Sending debug messages and tracking variable values in real-time. |
| **15. Logic** | Conditional statements (`If-Then-Else`), logical operators (`AND`/`OR`), comparators, negation (`NOT`), and ternaries. |
| **16. Loops** | Iterative structures: `For` loops, `Repeat While/Until`, and loop flow triggers (`Break`/`Continue`). |
| **17. Math** | Basic arithmetic, trigonometric functions, modulos, rounding, value constraints, and random numbers. |
| **18. Variables** | Creating, setting, and reading variable types (Integers, Floats, and Booleans). |
| **19. OLED Display** | Initializing screens, clearing, updating frame buffer, and drawing text, numbers, pixels, lines, or shapes. |
| **20. Ranging Sensors** | Initializing array sensors, configuring object avoidance, triggering proximity checks, and reading millimeter distance values. |

---

## 🚀 How to Release Guide Updates

Releasing a new version of the guide book is automated using GitHub Actions. Whenever a new tag is pushed, a workflow compiles the release bundle and publishes it to the GitHub repository.

### 📌 Tag Format
Releases are triggered by Git tags starting with **`v`** followed by semantic versioning.
* **Format:** `v<major>.<minor>.<patch>` (e.g. `v4.0.0`, `v4.0.2`, `v4.0.3-beta`)

### 🛠️ Release Steps
When you are ready to publish a new release:

1. **Commit all your changes** to the repository.
2. **Create a new git tag** matching the format:
   ```bash
   git tag v4.0.3
   ```
3. **Push the tag** to GitHub:
   ```bash
   git push origin v4.0.3
   ```

### ⚙️ Automation Workflow Details
Once the tag is pushed, the GitHub Action automatically:
1. Generates a `version.json` file referencing the pushed tag name and build timestamp.
2. Packages the entire project structure (HTML, style.css, assets directory `gbassets/`, and dependencies) into a single zip archive named **`guide.zip`** (excluding unnecessary files like `.git`, `.github`, and `node_modules`).
3. Creates a new GitHub Release with the tag name and attaches `guide.zip` as a release artifact.
