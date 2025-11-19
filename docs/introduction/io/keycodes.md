
# Keycodes

Keyboard input in the [Key Input](../../logic/nodes/key_input.md) and the
[Configure Controller](../../logic/nodes/configure_controller.md) nodes use
a custom code to reference keys that ensures that Kwyll keycodes are not
platform specific if at all possible. The scancodes are defined using a 
"section" and "index" mapping, that is similar to the Spectrum method of
mapping key presses to input codes, but is flexible enough that the same
mechanism can be used on other platforms. Each keycode is a 16 bit
integer with the high byte being the section number, and the low byte
being the index in that section. This is flexible enough to accommodate
a single section with 256 keys, or multiple sections with fewer keys.

The Kwyll keycodes for the Spectrum are split into 8 sections of 5 keys:


|   |   0   |   1   |   2   |   3   |   4   |
|---|-------|-------|-------|-------|-------|
| 0 | CAPS  |   Z   |   X   |   C   |   V   |
| 1 |   A   |   S   |   D   |   F   |   G   |
| 2 |   Q   |   W   |   E   |   R   |   T   |
| 3 |   1   |   2   |   3   |   4   |   5   |
| 4 |   0   |   9   |   8   |   7   |   6   |
| 5 |   P   |   O   |   I   |   U   |   Y   |
| 6 | ENTER |   L   |   K   |   J   |   H   |
| 7 | SPACE | SHIFT |   M   |   N   |   B   |


So, for exmaple, the scancode for "SPACE" is calculated as:

Row 7 in the high byte, and index 0 in the low byte, which in hexadecimal is:

    0x0700

or: 

    1792

in decimal.

