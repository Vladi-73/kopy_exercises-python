
Here's some dialog we want to show:

```text
- Are you hungry?
- Aaaarrrgh!
```

Let's try to display a string with this text:

```python
print("- Are you hungry?- Aaaarrrgh!")
# => - Are you hungry?- Aaaarrrgh!
```

As you can see, the result was not what we wanted. The lines are arranged one after the other, not one below the other. We need to somehow tell the interpreter to "press Enter" - to start a new line after the question mark. This can be done with the symbol `\n`:

```python
print("- Are you hungry?\n- Aaaarrrgh!")
# => - Are you hungry?
# => - Aaaarrrgh!
```

`\n` — is an example of an **escape sequence**. These sequences are also called control constructions. They can't be displayed in the same way as how they're typed.

When you type text in Word, you press Enter at the end of a line. The editor puts a special invisible character at the end of the line called LINE FEED (LF). In some editors, you can actually display the invisible characters. Then the text will look something like this:

```text
- Hey!¶
- Oh, hey!¶
- How's it going?
```

The device that outputs the corresponding text takes this character into account. For example, the printer drags the paper up one line when it encounters the LF, and the text editor drags all subsequent text below, also by one line.

There are several dozen such invisible characters, but in programming there are usually only a few. In addition to the line feed, there can also be:

* tab `\t` — the gap that you get when you press Tab
* carriage return `\r` — only works in Windows

You can recognize these control constructions in the text by the `\`. symbol. Programmers often use the line feed `\n` to properly format text. For example, if we write this code:

```python
print("Gregor Clegane\nDunsen\nPolliver\nChiswyck")
```

This will appear on the screen:

```text
Gregor Clegane
Dunsen
Polliver
Chiswyck
```

When working with the line feed symbol, consider the following points:

1. It doesn't matter what comes before or after `\n`: a character or an empty string. The line feed will be detected and executed in any case

2. A string can contain only `\n` and nothing else:
  ```python
  print('Gregor Clegane') # String with text
  print("\n") # String with an invisible line feed character
  print('Dunsen') # String with text
  ```

  The program will display this on the screen:

  ```text
  Gregor Ctextlegane


  Dunsen
  ```

3. In the code, the escape sequence `\n` looks like two characters, but from the interpreter's perspective, it's just one special character

4. If you want to output `\n` as text (two separate printable characters), you can use escaping - adding another `\` at the beginning. The sequence `\\n` will be displayed as the characters `\` and `n`, one after the other.

```python
print("Joffrey loves using \\n")
# => Joffrey loves using \n
```

Windows uses `\r\n` by default to start a new line. This combination works well on Windows, but creates problems when transferring to other systems. For example, when there are Linux users in the development team.

The point is that the sequence `\r\n` has a different interpretation depending on the chosen encoding, which we is something we'll talk about later. For this reason, it's customary among developers to always use `\n` without `\r`.

 In this case, the line feed is always treated the same and works fine in any system. Remember to configure your editor to use `\n`.
