# mpy_heb_date
Hebrew date in Micropython

## 1 Installation

Download the following two files and place them in the main folder of the controller:

**mpy_heb_date.py**

**gematria_pyluach.py** (from: https://github.com/simlist/pyluach/blob/master/src/pyluach/gematria.py)

On networked platforms it may alternatively be installed with
[mip](https://docs.micropython.org/en/latest/reference/packages.html).
```py
import mip
mip.install("github:sgbmzm/mpy_heb_date/package.json",target="/")
```

## 2 Example of basic usage
```py
import mpy_heb_date
A = get_today_heb_date_string()
print("today_heb_date_string", A)
```
There are many other useful functions. See the file: **mpy_heb_date.py**

**Please note: 

The Hebrew date is calculated from the controller's Gregorian date. If the Gregorian date is not set - the Hebrew date will not be set.
Calculations cannot be made for the year 2000 AD, but only from 2001 AD onwards.
Therefore, if your controller starts from its internal period which is in the year 2000, you will get an error. You must first set the internal clock to a date later than the year 2000**

```py
import machine
machine.RTC().datetime((2015, 3, 26, 4, 10, 59, 0, 0))  # (Year, month, day, day of the week, hour, minutes, seconds, subseconds)
```

**NOTE: I don't commit to addressing the problems because I don't have enough time.**

