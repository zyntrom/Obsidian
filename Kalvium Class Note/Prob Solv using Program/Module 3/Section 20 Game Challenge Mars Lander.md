I’ll give you **clean template codes in C++, Python, and Java** — all written in a **universal style** (no shortcuts, no cheat functions).

---

## ✅ C++ Solution

```c++
#include <iostream>
using namespace std;

int main() {
    int surfaceN;
    cin >> surfaceN; // number of points on the surface
    int landX, landY;
    for (int i = 0; i < surfaceN; i++) {
        cin >> landX >> landY; // surface points (not used in basic strategy)
    }
    // Game loop
    while (true) {
        int X, Y;        // current position
        int hSpeed, vSpeed; // horizontal & vertical speed
        int fuel;        // remaining fuel
        int rotate, power; // current rotation and thrust
        cin >> X >> Y >> hSpeed >> vSpeed >> fuel >> rotate >> power;
        // Strategy: 
        // Keep lander upright (rotate = 0)
        // Increase thrust if falling too fast
        int newRotate = 0;
        int newPower = 0;
        if (vSpeed <= -40) {
            newPower = 4; // maximum thrust to slow down
        } else {
            newPower = 2; // maintain some thrust
        }
        cout << newRotate << " " << newPower << endl;
    }
}

```

---

## ✅ Python Solution

```python
# Read surface points (not used in simple version)
surfaceN = int(input())
for _ in range(surfaceN):
    landX, landY = map(int, input().split())

# Game loop
while True:
    X, Y, hSpeed, vSpeed, fuel, rotate, power = map(int, input().split())

    # Strategy: keep lander upright
    new_rotate = 0
    new_power = 0

    if vSpeed <= -40:
        new_power = 4  # maximum thrust
    else:
        new_power = 2  # moderate thrust

    print(new_rotate, new_power)

```

---

## ✅ Java Solution

```java
import java.util.*;

public class MarsLander {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int surfaceN = in.nextInt();
        for (int i = 0; i < surfaceN; i++) {
            int landX = in.nextInt();
            int landY = in.nextInt();
        }
        // Game loop
        while (true) {
            int X = in.nextInt();
            int Y = in.nextInt();
            int hSpeed = in.nextInt();
            int vSpeed = in.nextInt();
            int fuel = in.nextInt();
            int rotate = in.nextInt();
            int power = in.nextInt();
            int newRotate = 0;
            int newPower;
            if (vSpeed <= -40) {
                newPower = 4; // max thrust
            } else {
                newPower = 2; // moderate thrust
            }
            System.out.println(newRotate + " " + newPower);
        }
    }
}

```

---

### 🔎 Explanation of the Logic:

- The **lander must land with**:
    - `|vSpeed| ≤ 40`
    - `|hSpeed| ≤ 20`
    - `rotate = 0°`
- Strategy in this simple version:
    - Always keep rotation = 0 (vertical).
    - If falling too fast (`vSpeed <= -40`), apply **full thrust (4)**.
    - Otherwise, maintain **moderate thrust (2)**.