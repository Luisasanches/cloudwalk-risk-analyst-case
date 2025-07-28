# Part 2.1 – Understanding the Payment Industry

## 1. Money and Information Flow in the Acquiring Market

In a card transaction, there are two main flows: the **information flow** (which happens in milliseconds) and the **money flow** (which takes a few business days).

###  Information Flow:
1. The customer enters their card details on a website or app.
2. The **payment gateway** securely transmits the transaction data.
3. The **sub-acquirer** (or directly the acquirer) receives and routes the data.
4. The **acquirer** forwards the request to the **card scheme** (e.g., Visa, Mastercard).
5. The **card scheme** sends it to the **issuing bank**, which approves or denies the transaction.
6. The response follows the same path back to the customer.

###  Money Flow:
1. Once approved, the **issuer** transfers the funds to the **acquirer**.
2. The acquirer/sub-acquirer deducts fees and sends the **net amount** to the merchant.
3. Settlement usually occurs within D+1, D+2, or D+30, depending on the merchant's contract.

###  Main Players:
- **Customer**: the cardholder.
- **Merchant**: sells goods/services.
- **Payment Gateway**: transmits transaction data.
- **Sub-acquirer**: facilitates payments for small merchants.
- **Acquirer**: processes and settles the transaction.
- **Card Scheme**: intermediary between acquirers and issuers.
- **Issuing Bank**: evaluates and authorizes or denies transactions.

---

## 2. Differences Between Acquirer, Sub-acquirer and Payment Gateway

###  Acquirer
- Licensed entity connected directly to card schemes.
- Holds contracts with merchants.
- Examples: Cielo, Rede, Getnet.

### Sub-acquirer
- Acts as an intermediary between small merchants and the acquirer.
- Provides an all-in-one solution with simplified onboarding.
- Examples: Stone, PagSeguro, CloudWalk (InfinitePay).

###  Payment Gateway
- A **technical bridge** that connects e-commerce platforms to processors.
- Does not handle funds or risk directly.
- Examples: Pagar.me, Iugu.

###  How the Flow Changes:
- With a **gateway**, the transaction still requires an acquirer or sub-acquirer to settle.
- A **sub-acquirer** eliminates the need for merchants to deal with acquirers or schemes directly.
- The **acquirer** is the one ultimately responsible for funds and transaction risk.

---

## 3. What are Chargebacks, How They Differ from Cancellations, and Their Connection to Fraud

###  Chargeback:
A chargeback is a **forced transaction reversal** initiated by the **issuing bank**, typically at the request of the cardholder. It is commonly used when a customer claims a transaction was unauthorized, fraudulent, or when a product/service was not received as expected. Chargebacks involve a formal dispute process and can result in financial loss for the merchant.

###  Cancellation:
A cancellation is initiated directly by the **merchant**, usually before settlement. It is a voluntary action that does not involve the issuing bank or any dispute process. Cancellations typically happen due to pricing errors, customer requests, or internal order issues.

###  Key Differences (in text form):
A **chargeback** is initiated by the cardholder through the issuing bank and typically involves a formal dispute process. It often takes several days or even weeks to resolve and is commonly associated with fraud (e.g., when a stolen card is used and the cardholder denies the transaction).

A **cancellation**, on the other hand, is initiated directly by the merchant, usually before the transaction is settled. It is voluntary, quickly processed, and not related to fraud in most cases.

In summary:
- **Chargebacks** are bank-driven, involve disputes, and are often fraud-related.
- **Cancellations** are merchant-driven, simple to process, and rarely fraud-related.

###  Fraud Connection:
Most fraudulent transactions (e.g., card-not-present fraud) end in chargebacks. Merchants who receive too many chargebacks may suffer financial losses, reputational damage, or even be banned from payment networks. That's why chargeback control is a critical part of risk management.
