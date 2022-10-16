# PPA Solutions

## Week 1

### PPA 1

```bash
mv *.txt level1
```

### PPA 2

```bash
file *
```

---

## Week 2

### PPA 1

```bash
echo file_{a..z}{a..z}{0..4}.txt > documents.txt
```

### PPA 2

```bash
ln /encryption/two-level/binary/positive-offset/encoding-key /ek
```

---

## Week 3

### PPA 1

```bash
ls -l *.txt > textFiles.txt 2> noFiles.txt && echo found
```

### PPA 2

```bash
cal -m $month > $month.txt 2> error.txt
```

### PPA 3

```bash
test 2> errorlog
test -e 2>> errorlog
test -n 2>> errorlog
```

---

## Week 4

### PPA 1

```bash
ls -l | grep "d......rwx" | grep -o "\S\+$"
```

### PPA 2

```bash
circle=`grep $pin Pincode_info.csv | grep -e ".* Circle" -o`
circle=${circle% Circle}
division=`grep $pin Pincode_info.csv | grep -e ",\w* Division" -o`
division=${division:1}
division=${division% Division}
echo $circle $division

# Alternative solution
# circle=`grep "$pin" Pincode_info.csv| grep -oP ".*(?= Circle)"`
# division=`grep "$pin" Pincode_info.csv| grep -oP "\w+(?= Division)"`
# echo $circle $division
```

---

## Week 5

### PPA 1

```bash
count=1
for var in "$@"; do
        if [ $((count%2)) -ne 0 ]; then
                echo -n "$var "
        fi

        ((count=count+1))
done
```

### PPA 2

```bash
  sum=0
  for i in $(cat result); do
    while read hash name; do 
      if [ $i == $hash ]; then
        inv=$(grep INVESTMENT $name)
        inv=${inv//INVESTMENT $/}
        sum=$((sum+inv))
      fi
    done < map
  done
  echo $sum
```

### PPA 3

```bash
if [ `cat data.txt | wc -l` -gt 16 ]; then
    echo "Yes"
else
    echo "No"
fi
```

---

## Week 1-5

### PPA 1

```bash
uname -a | grep "\bx.*\b" -o | cut -d ' ' -f1
```

### PPA 2

```bash
egrep "\bFAILED LOGIN\b" myauth.log | wc -l
```

### PPA 3

```bash
egrep "systemd-logind\[[0-9]+\]" myauth.log | grep user | cut -d " " -f 11 | cut -d "." -f 1 | sort | uniq
```

### PPA 4

```bash
grep "\bsession opened for user guest\b" myauth.log | tail -1 | cut -d " " -f 1-3
```

### PPA 5

```bash
egrep "\bsu\b" myauth.log | grep -v FAILED | egrep "\(to .*\)" -o | egrep "\b\w*\b" -o | grep -v to 
```

---
