[Open-Source](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FOpen-Source) [[Blockchain]] that uses [[Consensus Protocol]] to validate transactions

## How it works

1. A transaction is sent to the [Network](obsidian://open?vault=Obsidian&file=Tech%2FNetwork%2FNetwork) 
2. Indenpendent validators ([Nodes](obsidian://open?vault=Obsidian&file=Tech%2FCrypto%2FConcepts%2FNodes)) compile them in a list of transactions they believe to be true
3. The validators exchange those lists in rounds and vote to accept or reject lists
4. A transaction is validated if the approval is of at least 80% of validators (if not reached they are dropped or reconsidered)
5. All the transactions are applied to the [[Ledger]]

This proccess is repeated every 3-5 seconds, making it an extremely fast to transaction

Every one of the [Nodes](obsidian://open?vault=Obsidian&file=Tech%2FCrypto%2FConcepts%2FNodes) need access to the whole [[XRP Ledger]] to validate