## Why mock classes or functions (testing)

### Question

- If we create mock classes and test against them, then we are not actually testing our real code? What is the value of creating mock classes?

### Answers

- You use mocks when you want to test the interaction between the object you mocked and some function. It's the function you are actually testing, and how it might respond to an object in a specific state.

- For example, I might want to test what happens to my function when it receives an error from my network interface. So I will mock the interface to force it to return that error

- In other words we usually mock dependencies when unit testing to avoid testing anything other than our unit. We just provide some expected returns from our mock to mimic the scenarios we want to test

- So for example you might mock `useDispatch` from redux because if you're using redux, you should trust that their tests cover the actual functionality of useDispatch.

- When dealing with integration tests we can mock calls to 3rd party api's as well, so we can stage a service outage or slow response.

- Usually you create a mock function for 3 reasons:

- Mocking functions is useful for a few reasons. It will give your tests control over a function, meaning your tests will know if and when a function is called (sometimes you just wanna know/test that), and also now you can control the specific output of that function. Think about functions you create that make http calls to an API that you may or may not control. You don’t want your tests to fail because there were problems with your network connection. So you mock that function and make it return the data you expect, testing only that your app calls the function and does what it need to do with the response, useful for unit tests, integration tests and some end to end testing. But for real end to end testing you might wanna let your functions make some http calls and test the whole thing

1. To test that your OTHER code works.
2. To simulate a third-party function that you may not have access to while testing... Say an "expensive" API call.
3. Sometimes you're working on a large team and the function you're mocking up is really being built by someone else and it's not ready... so you mock it until they're done so you can continue your work.
