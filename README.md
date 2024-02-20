# zzlib.luau

Copyright (c) 2019-2024 by François Galea (fgalea à free.fr)

Copyright (c) 2024 by xhayper

This is a pure Luau implementation of a depacker for the zlib DEFLATE(RFC1951)/GZIP(RFC1952) file format.
zzlib.luau also allows the decoding of zlib-compressed data (RFC1950).

The implementation is pretty fast. It makes use of the built-in bit32 libraries for bitwise operations. Typical run times to depack Luau-0.613.tar.gz on a i5-12400F are 1.1s and time to depack lua-5.3.3.tar.gz are 0.18s.

zzlib.luau is distributed under the WT*PL licence. See the COPYING file for more details.

## Usage

### Read GZIP/zlib data from a string

Call the depacker, and get a string with the unpacked file contents, as follows:

```luau
-- import the zzlib library
local zzlib = require(path.to.zzlib)

if use_gzip then
  -- unpack the gzip input data to the 'output' string
  output = zzlib.gunzip(input)
else
  -- unpack the zlib input data to the 'output' string
  output = zzlib.inflate(input)
end
```
