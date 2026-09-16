[FDS_transaction_counter.py](https://github.com/user-attachments/files/32301997/FDS_transaction_counter.py)# Banking Fraud Detection System Project

[Uplodef check_transaction(amount, hour, new_device, distance_from_home):
    risk_score = 0
    reasons = [ ]

    # Calculate risk score based on input values
    if amount > 500:
        risk_score += 1
        reasons.append('Large transaction')

    if hour < 5:
        risk_score += 1
        reasons.append('Unusual transaction time')

    if new_device.lower() == 'yes':
        risk_score += 1
        reasons.append('New device')

    if distance_from_home > 100:
        risk_score += 1
        reasons.append('Unusual location')

    return risk_score, reasons

# Ask how many transactions the user wants to check
number_of_transactions = int(input('How many transactions would you like to check? '))

high_risk_count = 0
medium_risk_count = 0
low_risk_count = 0

for transaction in range(number_of_transactions):
    print()
    print('Transaction', transaction + 1)
    print('-----------------')

amount = float(input('Transaction amount (£): '))
hour = int(input('Transaction hour (0-23): '))
new_device = input('Is this a new device? (yes/no): ')
distance_from_home = float(input('Distance from home (km): '))

risk_score, reasons = check_transaction(
    amount,
    hour,
    new_device,
    distance_from_home
)

print('Risk score:', risk_score, '/ 4')


if reasons:
    print('Reasons:')
    for reason in reasons:
        print('-', reason)

if risk_score >= 3:
    print()
    print('HIGH RISK TRANSACTION')
    high_risk_count += 1
elif risk_score == 2:
    print()
    print('MEDIUM RISK TRANSACTION')
    medium_risk_count += 1
else:
    print()
    print('LOW RISK TRANSACTION')
    low_risk_count += 1


print()
print('BANKING FRAUD DETECTOR')
print('----------------------')

print('High risk:', high_risk_count)
print('Medium risk:', medium_risk_count)
print('Low risk:', low_risk_count)
ading FDS_transaction_counter.py…]()
