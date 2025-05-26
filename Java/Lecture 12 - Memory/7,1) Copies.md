[[6,1) Aliases]] <- Back
[[1) Dereferencing]] <- Next

---
## Copies
Copies, or copying more correctly, refers to the process of modifying an object WITHOUT changing the old one.
- To do this, a method will return a new object that might have some, or all, fields changed versus the object the copy was made from.

Suppose we have a class...
```java
class Account{
	int     userID;
	int     sortCode;
	double  balance;
	boolean isOverdraft
	
	String   userName;
	Currency accountCurrency;
	
	public Account(final int userID, final int sortCode, final double balance,
	final boolean isOverdraft, final String userName,
	final Currency accountCurrency){
		this.userID = userID;
		this.sortCode = sortCode;
		this.balance = balance;
		this.isOverdraft = isOverdraft;
		
		this.userName = userName;
		this.accountCurrency = accountCurrency;
	}
	//... other methods
}
```

Suppose some customer has multiple accounts under the same bank. They want to open a new one.
- Rather than having to ask a user ALL of their details again as input, the ones which already all exist can be copied from an existing account.
- To do this, a factory method can be used to create a new Account as long as the copying process is done.
- Ensure NO aliases exist. If an alias exists, one change to a single Account object will change them all.

```java
public Account createAccount(final Account existingAccount){
	return new Account(
		existingAccount.getUserID(),
		existingAccount.getSortCode(),
		0, //balanace set to 0 for new account.
		false, //isOverdraft set to false as balance = 0 by default.
		existingAccount.getUserName(),
		new Currency(
			existingAccount.getAccountCurrency().getSymbol(),
			existingAccount.getAccountCurrency().getCountryCode(),
			existingAccount.getAccountCurrency().getDailyExchangeRate()
		)
	);
}
```

This way, a copy is made. No aliases exist where they are NOT intended to exist.