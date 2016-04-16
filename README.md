# strong

Various string utilities for TorqueScript

### Unicode / UTF-8

#### `cp1252_to_utf8(str) → str`

Convert *str* from Torque's *"native"* string encoding (cp1252) to UTF-8, suitable for writing to a file or sending over the network.

#### `utf8_to_cp1252(str, error = "") → str`

Convert the UTF-8 encoded string *str* to an ordinary cp1252 string. Any Unicode character that cannot be represented in cp1252 will be replaced with *error*.

#### `utf8_len(str) → int`

Calculate the length (**in codepoints**, not glyphs or bytes) of the UTF-8 encoded string *str*.

#### `utf8_encode(cp: int) → str`

Encode the Unicode codepoint *cp* to a UTF-8 string.

#### `utf_decode(str) → int`

Decode the first Unicode codepoint found in *str*, and set `$utf8_i` to where the decoder left off (for decoding multiple characters). Returns `$UTF8_INVALID` when an invalid byte sequence is encountered.

### Bytes

#### From characters to numbers and back

`strpos($ord, %character) + 1` will get you the number representing `%character`.  
`$chr[%number]` will get you the character for `%number`.

For example:

```csharp
strpos($ord, "A") + 1 // → 65
$chr[65] // → "A"
```

#### Quick hex representation of byte

`$hex8[n]` is a two-character string defined for every `0 <= n <= 255`. For example, `$hex8[0x7a]` is `"7a"`.

### Various

#### `escapeBytes(str) → str`

#### `leftPad(str, len: int, pad) → str`

#### `rightPad(str, len: int, pad) → str`

#### `repeat(str, times: int) → str`

#### `strEndsWith(haystack, needle) → bool`

#### `striEndsWith(haystack, needle) → bool`

#### `strStartsWith(haystack, needle) → bool`

#### `striStartsWith(haystack, needle) → bool`

### Formatting

This probably isn't completely done.

#### `echof(fmt, ...)`

#### `warnf(fmt, ...)`

#### `errorf(fmt, ...)`

#### `format(fmt, ...) → str`
