## IBM Master The Mainframe 2020 - Entry
This was the first time when I have participated in any Master The Mainframe challenge. With no prior experience, this was the first time I have learnt about the mainfram and the core principles behind its working. Due to time shortage and lack of previous experience I wasn't able to make a very good project. But I'm still happy I was able to come up with this script which generates Credit Card Numbers, which are 100% compatible with Luhn's Algorithm.

### LuhnGen : Description

This REXX script generates random Credit Card Numbers which are fully compatible with Luhn's Algorithm

```  PARSE ARG incmplt_cc
  sum=0
  len_of_incomplt_ccard = LENGTH(incmplt_cc)
  do i = 1 to len_of_incomplt_ccard
    ints.i = SUBSTR(incmplt_cc,i,1)
    svaps = svaps || ints.i
  end
  do i = len_of_incomplt_ccard to 0 by -2
    j = ints.i
    j = j*2
    if j>9 then
      j = j//10 + 1
    ints.i =j
  end
  do i=0 to len_of_incomplt_ccard
    sum= sum + ints.i
  end
  if sum//10 = 0 then
    return 0
  else
    return 10-(sum//10)
```

This is the main part of the program which generates a check sum and applies it onto the generated numbers which in turn Makes it Luhn Compliant

The Final File can be found [here](https://github.com/monizb/MTM2020-LuhnGen/blob/master/luhn_cc_gen.rex).

## Screenshots

#### Generated Numbers:

![Output](https://github.com/monizb/MTM2020-LuhnGen/blob/master/screenshots/output.png)

#### Checking If Luhn Compliant:

![Compliant](https://github.com/monizb/MTM2020-LuhnGen/blob/master/screenshots/check.png)

#### Flyer:

![Flyer](https://github.com/monizb/MTM2020-LuhnGen/blob/master/screenshots/flyer.png)

