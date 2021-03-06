`ShouldNotBe` is the inverse of ShouldBe.

## Objects
`ShouldNotBe` works on all types and compares using `.Equals`.

``` csharp
var theSimpsonsCat = new Cat() { Name = "Santas little helper" };
theSimpsonsCat.Name.ShouldNotBe("Santas little helper");
```

Exception:
```
theSimpsonsCat.Name
    should not be
"Santas little helper"
    but was
"Santas little helper"
```

Want to contribute to Shouldly? [#304](https://github.com/shouldly/shouldly/issues/304) makes this error message better!

## Numeric
`ShouldNotBe` also allows you to compare numeric values, regardless of their value type.

``` csharp
const int one = 1;
one.ShouldNotBe(1)
```
Exception:
```
one should not be 1 but was 1
```

``` csharp
const long aLong = 1L;
aLong.ShouldNotBe(1);
```

Exception:
```
aLong should not be 1 but was 1
```
## DateTime(Offset)
`ShouldNotBe` DateTime overloads are similar to the numeric overloads and also support tolerances.

``` csharp
var date = new DateTime(2000, 6, 1);
date.ShouldNotBe(new DateTime(2000, 6, 1, 1, 0, 1), TimeSpan.FromHours(1.5));
```

Exception:
```
date
    should not be within
01:30:00
    of
01/06/2000 01:00:01
    but was 
01/06/2000 00:00:00
```
