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
diff passwords.old passwords.new
```

## Level 18

pass: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

```bash
ssh bandit18@bandit cat readme
```

## Level 19

pass: cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

## Level 20

pass: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

```bash
cat /etc/bandit_pass/bandit20 | netcat -lp 5555 &
~/suconnect 5555
```

## Level 21

pass: EeoULMCra2q0dSkYj561DX7s1CpBuOBt

```bash
cat $(cat /usr/bin/cronjob_bandit22.sh | tail -n 1 | cut -d" " -f4)
```

## Level 22

pass: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

```bash
cat $(cat /usr/bin/cronjob_bandit23.sh | sed "s/\$myname/bandit23/" | bash 2>/dev/null | cut -d" " -f5)
```

## Level 23

pass: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

```bash
mkdir -p /tmp/advik/
cd /tmp/advik
echo "mkdir -p /tmp/advik-pass24/; cat /etc/bandit_pass/bandit24 >> /tmp/advik-pass24/pass" > pass.sh
chmod +x pass.sh
cp pass.sh /var/spool/bandit24/foo/
seq 45 | xargs -I{} sh -c 'echo "please wait... {}/45"; sleep 1.5'
cat /tmp/advik-pass24/pass
```

## Level 24

pass: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

```bash
seq -w 0 9999 | xargs -I{} echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 {} | nc localhost 30002
```

## Level 25

pass: iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

```bash
cat ~/bandit26.sshkey

# let's find what shell level 26 is using
grep bandit26 /etc/passwd

# let's find out what does `/usr/bin/showtext` shell do
cat /usr/bin/showtext
# exec more ~/text.txt
# exit 0
# this "custom shell", just starts a pager and exits, so we have to break out of the `more` pager. more on this below.
```

## Level 26

pass: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

```bash
# ssh using the private key, shrink your terminal so that the `more` pager does not exit automatically
# press `v` to open the file in vi, and run the following vi commands to get a shell
# :set shell=/bin/bash
# :shell
# now that we have shell proper shell access, we can continue normally and find the passwd for next level
~/bandit27-do cat /etc/bandit_pass/bandit27
```

## Level 27

pass: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB

```bash

```
