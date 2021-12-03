# Date-Validator

```
export const dateValidator = (str?: string): boolean => {
  if (!str) return false;

  if (!new RegExp(dateRegEx).test(str.replace(/[/]/g, '-'))) {
    return false;
  }

  const splittedDate = str.split('/');

  const isLeapYear = isLeapYearValidator(Number(splittedDate[2]));

  if (isLeapYear) {
    return Number(splittedDate[0]) > 29 ? false : true;
  }

  return true;
};
```

# isLeapYearValidator

```
function isLeapYearValidator(year: number) {
  return (year % 4 == 0 && year % 100 != 0) || year % 400 == 0;
}

export const validateHour = (hour: string) => {
  return hourRegEx.test(hour);
};
```
