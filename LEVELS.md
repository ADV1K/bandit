## Level 0

pass: `N/A`

```bash
cat ~/readme
```

## Level 1

pass: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

```bash
cat ~/-
```

## Level 2

pass: `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

```bash
cat ~/--spaces\ in\ this\ filename--
```

## Level 3

pass: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

```bash
cat "inhere/...Hiding-From-You"
```

## Level 4

pass: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

```bash
bandit4@bandit:~$ find inhere -type f -exec grep "[a-zA-Z0-9]*" {} +
```

## Level 5

pass: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

```bash
find inhere -type f -size 1033c -exec cat {} \;
```

## Level 6

pass: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

```bash
find / -type f -size 33c -user bandit7 -group bandit6 -exec cat {} \;
```

Question: how to ignore files that you cannot read

## Level 7

pass: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

```bash
grep millionth data.txt
```

## Level 8

pass: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

```bash
sort data.txt | uniq -c | sort -n | head
```

## Level 9

pass: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

```bash
strings data.txt | grep =
```

## Level 10

pass: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

```bash
base64 -d data.txt
```

## Level 11

pass: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

```bash
cat data.txt | tr a-mn-zA-MN-Z n-za-mN-ZA-M
```

## Level 12

pass: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

```bash
cd $(mktemp -d)
xxd -r ~/data.txt | gzip -d | bzip2 -d | gzip -d | xxd -s 0x400 -l 217 | sed "s/000004/000000/" > 1.txt
xxd -r 1.txt | bzip2 -d | xxd -s 0x200 -l 76 | sed "s/000002/000000/" | xxd -r | gzip -d
```

PS: we search for the file signature on https://filesig.search.org/ to find out which program was used to commpress the file. (gzip and bzip2)
PS: we had to use xxd to take out the relevant chunk out of the binary file, rest was garbage.

## Level 13

pass: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

```bash
cat ~/sshkey.private
# save the above key, and then login via ssh to the next level
ssh -i ~/.ssh/id_bandit14 bandit14@bandit
```

## Level 14

pass: ssh-key

```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

## Level 15

pass: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

```bash
openssl s_client -ign_eof -connect localhost:30001
# then paste the password for the current level
```

## Level 16

pass: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

```bash
# find the port where the tcp server is running, should be one of the above between port 31000 and 32000
ss -tulpn | grep .*:3
# try connecting to all the ports above, and sending the password for current level, you'll eventually get a reply
openssl s_client -ign_eof -connect localhost:<dynamic>
```

## Level 17

pass: ssh-key

```bash

```
