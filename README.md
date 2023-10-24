# gmail-block-check
gmail-block-check is a script to fix and re-send emails redirected to gmail but blocked with a 550-5.7.1 code.

The problem: I use mail aliases in my private domain (e.g. `colas@nahaboo.net`) that redirect towards my actual mailbox, so that I can change email providers easily or use different email addresses for each of my online subscriptions, to fight spam. I am currently using Gmail.com for my actual "backend" mailbox, but some emails (spam or legit) are rejected by gmail with the error code `550-5.7.1`.

The solution: It seems that not having the actual gmail address in the To or CC fields, but my aliases, acts as "the straw that breaks the camel's back" for some internal spam detection system of gmail. Re-sending these emails with the aliases replaced in place by the actual gmail destination seems to allow them to pass. This bash script thus monitors the system mail log, and on detection of a `550-5.7.1` gmail rejection, fixes the email headers and re-send (once) to gmail. This is of course only  a guesswork, as gmail does not discloses what can trigger its 550-5.7.1 code, to avoid helping spammers to work around it.

Note: this repository is currently empty, a placeholder. I will upload the code and doc after the internal alpha test phase, I guess at the end of 2023.
