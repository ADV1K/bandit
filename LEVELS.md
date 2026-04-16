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

```
