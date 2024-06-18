# Mot de Fibonacci

Merci à Monsieur Frédéric Mansuy d'avoir suscité mon intérêt aux `mots de Fibonacci` grâce à son [post](https://www.linkedin.com/feed/update/urn:li:groupPost:1872005-7208727551576264704?commentUrn=urn%3Ali%3Acomment%3A%28groupPost%3A1872005-7208727551576264704%2C7208732223552770050%29&dashCommentUrn=urn%3Ali%3Afsd_comment%3A%287208732223552770050%2Curn%3Ali%3AgroupPost%3A1872005-7208727551576264704%29) sur LinkedIn;

Références: 
  
  - [Site web](https://supersymetrie.fr/) du concerné.
  - [Publication](https://drive.google.com/file/d/1WWkU34QpjkJl-bA4aUXaz9yZM_lBTVNR/view) pertinente toujours de Monsieur Frédéric Mansuy.
  - [Language D](https://dlang.org/)
  - Version éxécutable [online](https://onecompiler.com/d/42gkbtfrd)

## Code source

```d
import std.stdio;
import std.range;

string[] infiniteFibonacciWordSequence(uint k) {
    auto ifws = recurrence!"a[n-1]~a[n-2]"("S","L");
    return ifws.take(k).array;
}

void main() {
    foreach(i, ifwStr; enumerate(infiniteFibonacciWordSequence(8))) {
        writefln("m%d : %s (%d)", i+1, ifwStr, ifwStr.length);
    };
}
```

## Résultat

```txt
m1 : S (1)
m2 : L (1)
m3 : LS (2)
m4 : LSL (3)
m5 : LSLLS (5)
m6 : LSLLSLSL (8)
m7 : LSLLSLSLLSLLS (13)
m8 : LSLLSLSLLSLLSLSLLSLSL (21)
```
