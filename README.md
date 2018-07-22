# mathematica-encode
Imagine someone id giving you an awesome code. You want to analyze how it works, but when you look at it, it turns out to be

```
(*!1N!*)mcm
*#WyAFef9eath`UwFHOE49;C)RDE71Q3j/dYM9Da/OaAM*ou^)kw15h|T(+F>J'Me#1iO6
/>..Bf=vLDR4%}X0,5>"?Wd{ht"; |j.C.`:dT:<6\:+^SaDB6kwOHFosk z6JR`L}-TN8
KNT!6>L~Gbd}U%`m5Z_wX($!/&A}&l<W4'9]bmU7SLMS[,5Zlq(THSVf3%hjNB,0^)R}$=
iD>~LL#~iVE|aZBK[c1z6m\t.zSoCT(6>]<<eM[m"R.3+|:*8K\$_/Sa[T$W!y^&f=J>Rs
TYM9T6FpLSdMaY([m`qA!vLt/+#f;*&: g1lL]#goFSe3tKFK6IY9z(#>,c{-YY/H.S;OE
....
```

This random chars are a result of the [Encode](http://reference.wolfram.com/language/ref/Encode.html)
function of Mathematica. A way to make sure that your source code can not be directly edited. 

Because the security mechanism doesn't use any keys it relies solely on security by obscurity. The safety of this function has already been [discussed](https://mathematica.stackexchange.com/questions/3199/how-safe-is-encode).

When I saw this function I took it as a challenge and tried to decrypt it via an ordinary known plaintext attack. It took around 8 hours when the unencrypted code appeared on my screen.

This code here, written in Python shows the encoding function. First it compresses every char by using Huffman encoding and a fixed internal table. It then encodes the bitstream to some sort of two-byte base 95 compression.

The decoding function is not part of this repository. Feel free to revert my code :-)


