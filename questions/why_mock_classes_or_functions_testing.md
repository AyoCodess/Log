## Why mock classes or functions (testing)

### Question

- If we create mock classes and test against them, then we are not actually testing our real code? What is the value of creating mock classes?

### Answer

- You use mocks when you want to test the interaction between the object you mocked and some function. It's the function you are actually testing, and how it might respond to an object in a specific state.

- For example, I might want to test what happens to my function when it receives an error from my network interface. So I will mock the interface to force it to return that error
