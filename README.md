# Project Custom from vPhon for convert Raw text to IPA

* Use for embeding TTS model using Tacotron2

* By using IPA, tacotron2 can deal with cases cross language as a proposal from futre paper

* Include diary research in phoneme of Vietnamese, painful and character of Viet

* Function include: Convert Grapheme to IPA, List same token output, normalize text with vinorm and wordtoken

* Requirment: vinorm, underthesea, eng_to_ipa

```
pip install vinorm
pip install underthesea
pip install eng_to_ipa
pip install git+git://github.com/quadrismegistus/prosodic.git
```

Usage:

```python
from viphoneme import vi2IPA
phoneme = vi2IPA("Được viết vào 6/4/2020, có thể xử lí những trường hợp chứa English")

>> dɯək6 viət5 vaw2 ʂăw5 tʰaŋ5 bon5 năm1 haj1 ŋin2 xoŋ͡m1 ʈăm1 haj1_mɯəj1 , kɔ5_tʰe4 sɯ4_li5 ɲɯŋ3 ʈɯəŋ2_hɤp6 cɯə5 ˈɪŋlɪʃ
```
Function to convert to phoneme with option split each element
```python
from viphoneme import vi2IPA_split
delimit ="/"
vi2IPA_split("Được viết vào 6/4/2020, có thể xử lí những trường hợp chứa English", delimit)

>> /d/ɯə/k/6/ /v/iə/t/5/ /v/a/w/2/ /ʂ/ă/w/5/ /tʰ/a/ŋ/5/ /b/o/n/5/ /n/ă/m/1/ /h/a/j/1/ /ŋ/i/n/2/ /x/o/ŋ͡m/1/ /ʈ/ă/m/1/ /h/a/j/1/_/m/ɯə/j/1/ /,/ /k/ɔ/5/_/tʰ/e/4/ /s/ɯ/4/_/l/i/5/ /ɲ/ɯ/ŋ/3/ /ʈ/ɯə/ŋ/2/_/h/ɤ/p/6/ /c/ɯə/5/ /ɪ/ŋ/l/ɪ/ʃ/ /./
```

Parsing, split phoneme element, with listParse is list of avaible symbol, delimit is symbol to split each element
```python
Parsing(listParse, text, delimit)
```

Get list of symbol using for represent phoneme
```python
from viphoneme import syms
print(syms)
```