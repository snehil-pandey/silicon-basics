# What is Binary?
Binary is the **language of computers**.  
It uses only 2 symbols:  
- 0 &rarr; OFF (*no electricity*)
- 1 &rarr; ON (*electricty flowing*)

Every piece of data is just a giant pattern of 0s and 1s.  
Example: `01001000 01101001` represents *Hi*.  

# Why computer use binary?
Just because it's made up of transistors (*tiny electrical switches*).  
A transistor can be:  
- ON &rarr; 1
- OFF &rarr; 0

That's it!
Binary = Electricity Pattern.

# What is a Bit and Byte?
- 1 bit = 0 or 1
- 8 bits = 1 Byte

Example: `01100001`  
This is the representation of 'a' in text.  

# How numbers are stored in Binary?
Numbers are stored using **place value system**, like decimal (base 10), but binary is base 2.  

Few Examples:
`1000` &rarr; 8  
`100` &rarr; 4  
`11`  &rarr; 3  

**Conversion formula:**
It's better if we take an example: `1101`  
let's learn it interactively  
| Bits        | 1 | 1 | 0 | 1 |
|-------------|---|---|---|---|
| Place Value |$2^3$|$2^2$|$2^1$|$2^0$|  

now multiply each of the corresponding values like:  
$$2^0 * 1 + 2^1 * 0 + 2^2 * 1 + 2^3 * 1$$  
$$= 1 + 0 + 4 + 8$$  
$$= 13$$

Remember start from leftmost bit to the rightmost bit and multiply it with the place value which is like  
$\ldots, 2^3, 2^2, 2^1, 2^0$  

# How texts is stored (ASCII & Unicode)
Computer maps each letter to number(base 10) then stores it in binary.  
Example (ASCII):  
- A = 65 => `01000001`
- a = 97 => `01100001`

So text is just numbers in binary.  

Unicode is the mordern version that supports emojis, all languages, symbols, etc.  

# How images are stored?
Images are made of **pixels** (tiny squares).  
Each pixel has:  
- a color (stored in RGB values)
- each RGB value is 0-255
- each value fit in *one byte*

Example: `RGB(255, 100, 30)` is:
```text
R: 11111111
G: 01100100
B: 00011110
```

So 1px = 3 B = 24 b (px &rarr; pixel; B &rarr; byte; b &rarr; bit)  

An HD image with `1920 x 1080 pixels` has **2073600 pixels** => 2M x 3 B ⁓ 6MB  
This is why bigger image = bigger file size.  

# How audio is stored?
Sound is tored as *waveform sampled many times per second*.  

Example:
- a CD audio uses 44,100 samples per second
- eeach sample is a number
- That number is again stored in binary (usually 16-bit or 24-bit)

More samples = better quality

~ for today this much only next time video, general files, etc ~
