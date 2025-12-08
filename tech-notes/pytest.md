# PyTest

## Unit Test framework

- pytest is a framework for unit testing in python
- Alternative to the python built in unittest
- Aims to be easier to use
- Publishes on PyPI as `pytest`

## Terms and definitions

- **Unit Test:** Tests one unit of a system. May but not has to be a method or class. Goal is to verify every unit of a system works as expected. (see [[software-testing]])
- **Test case:** #todo

## Best practices

- **Naming conventions:**
  - **Test script:** `test_<script to be tested>.py`
  - **Test method:** `test_<method to be tested>`
- **Code structure:**
  - One test method for each logic to be tested (can be 1..n for one method to be tested)

## Quickstart: How to create a test?

### 1. **Create test file**

- Create new python file 
- Naming convention: `test_<file to be tested>.py`
- Import file to be tested

### 2. **Write test methods**

**Method header:**

- Write a test method for each method to be tested
- Naming convention: `test_<method to be tested>`
  - But if different logic is tested, create two testing methods! even if you test just one method!

**Method body:**

- Call/use the function to be tested

**Use of `assert`**

- `assert <actual output> == <correct output>, "test explanation"`
- Compare the actual output with the correct output by doing an _assertion_
- An assertion evaluates to `True` or `False` for a passed or failed test case
- And in case of a failed test, the test explanation is given

## **Execute test:**

```bash
pytest <test_script>.py
```

## PyTest concepts to write good tests 

### _asserts_ and _raises_

Baisc unit testing tests two things:

- **assertions:** Is a value as expected? (With `assert`)
- **raises:** Do the errors I expect to be raised actually get raised? (with `pytest.raises`)

### Fixtures

- Setup method to be run before each test whose result can be passed as argument to the test method
- To give a fresh set of data to test with and to avoid one test affecting another

```python
@pytest.fixture
def some_fixture():
    return some_object

def test_some_test(some_fixture):
    assert some_fixture.do_something() == "hi"
```

### Parameterized testing

- Specify parameters for test methods as decorator
- So that all values defined in the decorator get passed as argument to the test method

```python
@pytest.mark.parametrize("param1", "param2", [
    (<param1 possibility 1>, <param2 possibility 1>),
    (<param1 possibility 2>, <param2 possibility 2>),
    ...
])

# Gets called with each value of the list above 
def test_mytest(param1, param2):
    assert mymethod(param1) == param2
```

### Mocks

**What are Mocks?**

- Simulate objects that are used in code
- Used when code has external dependencies like and API or Database
- Then the corresponding API or Database objects are mocked to only test the functionality of the code and not the external dependency
- As a Unit test is not supposed to fail when the API or Database is down, as a Unit test only test a particular isolated unit of a system

**How are Mocks used in pytest?**

- Automatically passed as argument to the test method when specified as parameter `mocker`
- Can mock only specified objects or method with `mocker.patch`
- Or can mock entire classes with `mocker.Mock(spec=My_class())`
- In both cases, in the code the mocked object is used instead of the real one

- Allows to specifiy the return value of that by using `my_mocked_object.some_method.return_value`

```python
def test_mytest(mocker):
    mocker_get = mocker.patch(requests.get)
    mocker_get.return_value.status_code = 200
    mocker_get.return_value.json.return_value = {"something": 1, "someotherthing": 2}

def test_myothertest(mocker)
    mock_someclass = mocker.Mock(spec=Some_class())
```

[software-testing]: software-testing.md "Software testing"
