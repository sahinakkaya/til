You can define methods outside of class definition. However, you need to make sure that you bound the method *to the class* itself **not** instance.

```python
class Foo:
    x = 42


def bar(self):
    return self.x


if __name__ == "__main__":
    foo = Foo()

    Foo.bar = bar
    print(foo.bar())  # 42

    foo.bar = bar
    print(foo.bar())  # error, because `bar` doesn't know about `self`
```
