# Command Manager

Wrapper around `argparser` to simplify creating command line interfaces.

## Installation

```bash

python setup.py install

```

## Example

Use `option` decorator to create sub command which execute decorated function.

```python

from command_manager import Manager


manager = Manager()

@manager.option('--test', type=int):
def sub_command1(test):
    print(test)

@manager.option('--file', dest='file_name', type=str)
def sub_command2(file_name):
    print('File {}'.format(file_name))


if __name__ == '__main__':
    manager.run_command()

```
