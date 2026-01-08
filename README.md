# Smart Home Automation System

An intelligent energy management solution designed to optimize household energy consumption through automated control of smart devices based on environmental conditions, occupancy detection, and time schedules.

## 🎯 Project Overview

This system demonstrates how IoT devices can work together to reduce energy consumption without compromising user comfort. The implementation achieves up to **51% reduction in power consumption** through intelligent automation logic.

## ✨ Features

### Smart Devices
- **Smart Lights**: Adjustable brightness (0-100%) and color modes (warm white, bright white, auto)
- **Smart Thermostat**: Adaptive heating/cooling with temperature-based power adjustment
- **Smart Plugs**: Control non-smart appliances (demonstrated with coffee machine)
- **Automated Window Shutters**: Temperature and time-based position control
- **Motion Sensors**: Occupancy detection for device activation
- **Temperature Sensors**: Environmental monitoring for climate control

### Energy Optimization Logic
- **Lights**: Automatically dim to 60% brightness during nighttime (6 PM - 6 AM) when motion detected, off otherwise
- **Thermostat**: Operates at 50-75% power based on temperature differential from target, turns off when unoccupied
- **Coffee Machine**: Active only during morning hours (6 AM - 12 PM) with motion detection
- **Shutters**: Close at night for privacy, respond to temperature (close >30°C, open <25°C)

## 🏗️ Architecture

The system uses object-oriented design with:
- **Inheritance**: Device → Sensor → MotionSensor/TemperatureSensor
- **Composition**: HomeAutomationSystem aggregates all devices
- **Extension**: EnergyEfficientHome extends base system with optimization

### Class Hierarchy
```
Device (Parent)
├── SmartLight
├── SmartThermostat
├── SmartPlug
├── AutomatedWindowShutter
└── Sensor
    ├── MotionSensor
    └── TemperatureSensor

HomeAutomationSystem (Composition)
└── EnergyEfficientHome (Extension with Optimization)
```

## 📁 Project Structure

```
smart-home-automation/
├── home_network.py            # Core implementation (Device classes + optimization)
├── home_network_tests.py      # Unit tests (>90% coverage)
├── Home automation code.ipynb # Jupyter notebook with simulations
├── README.md                  # This file
└── docs/
    └── UML_diagram.png       # System architecture diagram
```

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.13 or higher
```

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/smart-home-automation.git
cd smart-home-automation
```

2. No additional dependencies required (uses Python standard library)

### Running the System

#### Basic Simulation
```python
from home_network import HomeAutomationSystem

# Create system instance
system = HomeAutomationSystem()

# Control all devices
system.turn_all_on()
system.show_status()

# Get total power consumption
total_power = system.get_total_power_consumption()
print(f"Total Power: {total_power:.2f} W")
```

#### Energy Optimization
```python
from home_network import EnergyEfficientHome

# Create optimized system
system = EnergyEfficientHome()

# Run optimization
system.optimise_energy_usage()

# Compare before/after
before, after = system.optimise_and_compare()
print(f"Power reduced from {before:.2f}W to {after:.2f}W")
```

### Running Tests
```bash
python home_network_tests.py
```

## 📊 Results

### Power Consumption Analysis
- **Before Optimization**: ~2308W (all devices active)
- **After Optimization**: ~1126W (intelligent control)
- **Savings**: Up to 51% reduction

### Test Coverage
- 28 comprehensive unit tests
- >90% code coverage
- Tests for both Stage 1 (basic functionality) and Stage 2 (optimization logic)

## 🧪 Testing

The test suite validates:
- ✅ Device reset functionality
- ✅ Random state settings
- ✅ Power consumption calculations
- ✅ Extreme condition handling (brightness limits, temperature modes)
- ✅ Motion-based light control
- ✅ Time-based appliance scheduling
- ✅ Temperature-responsive shutter automation
- ✅ Thermostat power reduction logic
- ✅ Total system power optimization

## 🛠️ Technical Details

### Key Technologies
- **Language**: Python 3.13
- **Development**: Jupyter Notebook
- **Testing**: unittest framework
- **Design Patterns**: OOP (Inheritance, Composition, Polymorphism)

### Device Power Specifications
| Device | Base Power | Notes |
|--------|-----------|-------|
| Smart Light | 10W | Varies with brightness/color |
| Smart Thermostat | 1500W | Heating: 100%, Cooling: 120% |
| Smart Plug | 0.2W | Plus attached device power |
| Window Shutter | 5W | Only during movement |
| Motion Sensor | 0.5W | Continuous operation |
| Temperature Sensor | 0.5W | Continuous operation |
| Coffee Machine | 800W | When attached to plug |

## 🔮 Future Enhancements

- **Machine Learning**: Predictive control based on user habits
- **Solar Integration**: Optimize renewable energy usage
- **Mobile App**: Remote access and real-time notifications
- **Voice Control**: Integration with smart assistants
- **Analytics Dashboard**: Energy usage visualization and insights
- **Multi-room Support**: Scale to whole-house automation

## 📝 Documentation

For detailed project documentation including methodology, results, and UML diagrams, see the full report in `docs/` folder.

## 👤 Author

**Dr. Harsha Padmanabhan**
- Course: ENGR8800 
- Date: October 31, 2025

## 📄 License

This project is part of an academic assignment. Feel free to use for educational purposes.

## 🤝 Contributing

This is an academic project, but suggestions and feedback are welcome! Feel free to open an issue or submit a pull request.

## 📧 Contact

For questions or collaboration opportunities, connect with me on [LinkedIn](https://www.linkedin.com/in/harsha-padmanabhan-phd-49059b55/).

---

⭐ If you found this project interesting, please consider giving it a star!
