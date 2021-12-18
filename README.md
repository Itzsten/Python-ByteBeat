# Python-ByteBeat
Making your first ByteBeat in Python:
```py
from ByteBeat import *
ByteBeat.Play(
    't%0.81*t', # The mathematical input, as a string.
    10,         # The amount of seconds to play.
    8000,       # KiloHertz (kHz) for the ByteBeat.
    True        # Wait until the ByteBeat finished or not.
)
```
Let's say you want to generate the ByteBeat buffering before playing it, i.e playing multiple ByteBeats after each other without needing to wait for the other ones to generate.
```py
beats = []
beats.append(ByteBeat.GenerateBuffer('sin(sin(t/100)-t/((2+(t>>10&t>>12)%9)))*64+128', 5, 8000))
beats.append(ByteBeat.GenerateBuffer('t%0.81*t', 5, 8000))
for beat in beats:
	ByteBeat.PlayFromBuffer(beat, 5, 8000, True)```
