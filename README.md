# Pomodoro

A Unix command line pomodoro timer.

## Usage

`./pomodoro` will start a pomodoro timer that will last, by default, for 25
minutes.

When `pomodoro` is supplied with an argument, it will last that number of
minutes. For example, if you wanted a pomodoro that lasted 15 minutes, you would
type `./pomodoro 15`.

30 seconds before the pomodoro is about to finish, it will use `notify-send` to
send a notification saying that there are "30 seconds left".

It's also possible, thanks to the command line, to use this timer in conjunction
with other programs. This example will lock your computer (if you're using the
i3 window manager) once the pomodoro has ended.

```
./pomodoro && i3lock
```

Thanks to the `pomodoro` outputting to `stdout`, as explained below, you can log
the number of pomodoros you have done to a file.

```
./pomodoro >> pomodoro_log.txt
```

You can combine these two things to log and lock.

```
./pomodoro >> pomodoro_log.txt && i3lock
```

## Output Format

When the `pomodoro` terminates, whether that is naturally or with Ctrl+C, then
it will output to `stdout` in the following format: `YY-mm-dd:HH-MM-SS:SECONDS`.

Example: `2017-05-27:15-29-15:1500`.

Therefore, the three sections are `DATE:TIME:SECONDS`. The date-time is the time
at which the pomodoro started and `SECONDS` is the number of seconds that the
pomodoro lasted for.

## Author

Jordan Lord

## License

GNU General Public License Version 3
