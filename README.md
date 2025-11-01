# ...existing code...
import sys

def main():
    try:
        a = float(input("Enter first number: ").strip())
        b = float(input("Enter second number: ").strip())
    except ValueError:
        print("Invalid number input.")
        sys.exit(1)

    op = input("Enter operation (+, -, *, /): ").strip().lower()

    if op in ("+", "add", "addition"):
        res, sym = a + b, "+"
    elif op in ("-", "sub", "subtract"):
        res, sym = a - b, "-"
    elif op in ("*", "x", "mul", "multiply"):
        res, sym = a * b, "*"
    elif op in ("/", "div", "divide"):
        if b == 0:
            print("Error: Division by zero.")
            sys.exit(1)
        res, sym = a / b, "/"
    else:
        print("Unknown operation.")
        sys.exit(1)

    # Print integer-looking results without trailing .0
    def fmt(n):
        return int(n) if n.is_integer() else n

    print(f"{fmt(a)} {sym} {fmt(b)} = {fmt(res)}")

if __name__ == "__main__":
    main()
# ...existing code...# calculator1
