# Regression file for [this test](test/subgroups/test_subgroups.py:724)

Given Source code:

```python
@dataclasses.dataclass
class ConfigWithFrozen(TestSetup):
    conf: FrozenConfig = subgroups({"odd": odd, "even": even}, default=odd)

```

and command: '--conf=even --a 100 --help'

We expect to get:

```console
usage: pytest [-h] [--conf {odd,even}] [-a int] [-b str]

options:
  -h, --help         show this help message and exit

ConfigWithFrozen ['config_with_frozen']:
  ConfigWithFrozen(conf: 'FrozenConfig' = 'odd')

  --conf {odd,even}  (default: odd)

FrozenConfig ['config_with_frozen.conf']:
  FrozenConfig(a: 'int' = 1, b: 'str' = 'bob')

  -a int, --a int    (default: 2)
  -b str, --b str    (default: even)

```