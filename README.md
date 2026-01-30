# green_environment
# User inputs
num_classrooms = int(input("Enter number of classrooms: "))
num_fans = int(input("Enter number of fans: "))
num_lights = int(input("Enter number of lights: "))
ac_hours = float(input("Enter AC hours per day: "))

# Assumptions
fan_power = 75  # W
light_power = 40  # W
ac_power = 1000  # W per AC
daily_hours = 8  # assumed hours for fans and lights

# Calculations
fan_energy = num_fans * fan_power * daily_hours / 1000  # kWh
light_energy = num_lights * light_power * daily_hours / 1000  # kWh
ac_energy = num_classrooms * ac_power * ac_hours / 1000  # kWh
total_energy = fan_energy + light_energy + ac_energy

print(f"Total daily energy usage: {total_energy:.2f} kWh")

# AI Suggestions
suggestions = []
if ac_hours > 6:
    suggestions.append("Reduce AC usage to below 6 hours per day by optimizing room temperatures.")
if num_fans > num_classrooms * 2:
    suggestions.append("Consider installing energy-efficient fans or reducing fan count.")
if num_lights > num_classrooms * 10:
    suggestions.append("Switch to LED lights and ensure lights are turned off when not in use.")
if total_energy > 100:
    suggestions.append("Implement smart sensors to automate lighting and AC based on occupancy.")

if suggestions:
    print("Optimization Strategies:")
    for s in suggestions:
        print(f"- {s}")
else:
    print("Energy usage is optimal. Keep up the good work!")
