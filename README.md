# Simple Stock Portfolio Tracker

# Hardcoded stock prices
prices = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOG": 140,
    "MSFT": 320,
    "AMZN": 150
}

print("=== Stock Portfolio Tracker ===")
print("Available stocks and their prices:")

for s, p in prices.items():
    print(f"{s}: {p}")

total = 0

while True:
    stock = input("\nEnter stock symbol (or 'done' to finish): ").upper()

    if stock == "DONE":
        break

    if stock not in prices:
        print("Stock not found. Try again.")
        continue

    qty = input(f"Enter quantity of {stock}: ")

    if not qty.isdigit():
        print("Quantity must be a number.")
        continue

    qty = int(qty)
    value = qty * prices[stock]
    total += value

    print(f"Added: {qty} × {stock} = {value}")

print("\n=== Final Portfolio Summary ===")
print(f"Total investment value: {total}")
