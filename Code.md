# Завдання 1
def calculate_area(length, width):
    return length * width

rectangles = []
for i in range(3):
    length = float(input(f"Введіть довжину сторони прямокутника {i+1}: "))
    width = float(input(f"Введіть ширину сторони прямокутника {i+1}: "))
    area = calculate_area(length, width)
    rectangles.append(area)
    print(f"Площа прямокутника {i+1}: {area}")
import math

#Завдання 2

def calculate_hypotenuse(a, b):
    return math.sqrt(a**2 + b**2)
a1 = float(input("Введіть перший катет першого трикутника: "))
b1 = float(input("Введіть другий катет першого трикутника: "))
a2 = float(input("Введіть перший катет другого трикутника: "))
b2 = float(input("Введіть другий катет другого трикутника: "))
hypotenuse1 = calculate_hypotenuse(a1, b1)
hypotenuse2 = calculate_hypotenuse(a2, b2)
print(f"Гіпотенуза першого трикутника: {hypotenuse1}")
print(f"Гіпотенуза другого трикутника: {hypotenuse2}")

if hypotenuse1 > hypotenuse2:
    print("Гіпотенуза першого трикутника більша.")
elif hypotenuse1 < hypotenuse2:
    print("Гіпотенуза другого трикутника більша.")
else:
    print("Гіпотенузи обох трикутників рівні.")
  #Завдання 3
def is_inside_circle(x, y, a, b, R):
    return (x - a)**2 + (y - b)**2 < R**2

a = float(input("Введіть координату x центра кола: "))
b = float(input("Введіть координату y центра кола: "))
R = float(input("Введіть радіус кола: "))

p1, p2 = map(float, input("Введіть координати точки P (через пробіл): ").split())
f1, f2 = map(float, input("Введіть координати точки F (через пробіл): ").split())
l1, l2 = map(float, input("Введіть координати точки L (через пробіл): ").split())

points = [(p1, p2), (f1, f2), (l1, l2)]
inside_count = 0

for i, (x, y) in enumerate(points, start=1):
    if is_inside_circle(x, y, a, b, R):
        inside_count += 1
        print(f"Точка {chr(80+i-1)} лежить всередині кола.")

print(f"Кількість точок, що лежать всередині кола: {inside_count}")

#Завдання 4

def calculate_quadrilateral_area(X, Y, Z, T):
    triangle_area = 0.5 * X * Y
    semi_perimeter = (Z + T + (X**2 + Y**2)**0.5) / 2
    triangle2_area = (semi_perimeter * (semi_perimeter - Z) * (semi_perimeter - T) * (semi_perimeter - (X**2 + Y**2)**0.5)) ** 0.5
    return triangle_area + triangle2_area

X = float(input("Введіть довжину сторони X: "))
Y = float(input("Введіть довжину сторони Y: "))
Z = float(input("Введіть довжину сторони Z: "))
T = float(input("Введіть довжину сторони T: "))

area = calculate_quadrilateral_area(X, Y, Z, T)
print("Площа чотирикутника: {area}")
#Завдання 5
def find_numbers(n, nums):
    result = []
    for i in range(1, n+1):
        if all(i % num == 0 for num in nums):
            result.append(i)
    return result

n = int(input("Введіть значення n: "))
nums = list(map(int, input("Введіть числа, через які має ділитися n (через пробіл): ").split()))

result = find_numbers(n, nums)
print(f"Натуральні числа, що не перевищують {n} і діляться на кожне з чисел {nums}: {result}")

