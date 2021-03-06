## Wait

Wait functions provide simple wait capabilities. The OS scheduler puts the current thread in `waiting state`, allowing another thread to execute. Even better: If there are no other threads in `ready state`, it can put the whole microcontroller to `sleep`, saving energy.

```
/** Waits for a number of seconds, with microsecond resolution (within
 *  the accuracy of single precision floating point).
 *
 *  @param s number of seconds to wait
 */
void wait(float s);

/** Waits a number of milliseconds.
 *
 *  @param ms the whole number of milliseconds to wait
 */
void wait_ms(int ms);

/** Waits a number of microseconds.
 *
 *  @param us the whole number of microseconds to wait
 */
void wait_us(int us);
```

### Avoiding OS delay

When you call `wait`, your board's CPU is in a loop waiting for the required time to pass. Using the [Arm Mbed RTOS](/docs/development/reference/rtos.html), you can make a call to `Thread::wait` instead.

### Example

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/wait_ex_1/)](https://os.mbed.com/teams/mbed_example/code/wait_ex_1/file/7d249aa3d880/main.cpp)

### Related content

- [RTOS](/docs/development/reference/rtos.html) overview.
