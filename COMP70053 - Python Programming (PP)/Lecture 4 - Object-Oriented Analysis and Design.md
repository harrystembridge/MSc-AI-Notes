---
flashcards:
  q-xg32: { nid: 1792505929896, hash: hb2djfhd, sync: yn3c7vrn }
  q-6bri: { nid: 1792505929952, hash: ns4prv37, sync: kvxgkz4d }
  q-6gcz: { nid: 1792505930005, hash: mv4x5fki, sync: bnf78v4m }
  q-kiau: { nid: 1792505930054, hash: qw4mdhnk, sync: 27f8kwqw }
  q-as3r: { nid: 1792505930103, hash: py7948aq, sync: hncn5gf8 }
  q-5873: { nid: 1792505930151, hash: 5ccyk4ky, sync: 83zp2fsj }
  q-czut: { nid: 1792505930202, hash: xkki66s3, sync: ip6xkr2a }
  q-r8kg: { nid: 1792505930252, hash: g6u7i52y, sync: 7endxycz }
  q-2yxm: { nid: 1792505930305, hash: r4tnmcib, sync: f7trsqcb }
  q-acid: { nid: 1792505930354, hash: vrtawib3, sync: a9uztibr }
  q-wbsh: { nid: 1792505930406, hash: pnbar9rs, sync: spiauyfx }
---

![[PP - Lecture 4.pdf]]
#examinable


![[PP - Lecture 4.pdf#page=15|PP - Lecture 4, page 15]]


> [!CARD] What is a UML class diagram?
> A static diagram showing a system's classes (name, attributes, methods) and the relationships between them.
^q-xg32

> [!CARD] What are the three compartments of a class box in a UML class diagram?
> Top: class name. Middle: attributes. Bottom: methods (operations).
^q-6bri

> [!CARD] What do the visibility symbols `+`, `-`, `#` mean in UML?
> `+` public, `-` private, `#` protected.
^q-6gcz

> [!CARD] What is an association in UML?
> A general "uses/knows about" relationship between two classes, drawn as a plain line (optionally with an arrow for direction). Neither object owns the other and their lifetimes are independent.
^q-kiau

> [!CARD] What is aggregation in UML?
> A "has-a" whole–part association where the part can exist independently of the whole. Drawn with a hollow (empty) diamond at the whole's end. E.g. a Team has Players, but Players exist without the Team.
^q-as3r

> [!CARD] What is composition in UML?
> A strong "has-a" whole–part relationship where the part cannot exist without the whole; if the whole is destroyed, so are its parts. Drawn with a filled diamond at the whole's end. E.g. a House and its Rooms.
^q-5873

> [!CARD] What is the difference between aggregation and composition?
> Aggregation: parts can outlive the whole (hollow diamond). Composition: parts' lifetime is tied to the whole (filled diamond).
^q-czut

> [!CARD] What is the difference between association and aggregation?
> Association is a general link between peer classes; aggregation is a more specific whole–part ("has-a") association.
^q-r8kg

> [!CARD] What is inheritance (generalisation) in UML?
> An "is-a" relationship where a subclass inherits from a superclass. Drawn as a line with a hollow triangle arrowhead pointing to the superclass.
^q-2yxm

> [!CARD] What is a dependency in UML?
> A weak "uses" relationship where one class temporarily depends on another (e.g. as a method parameter). Drawn as a dashed arrow pointing to the class depended on.
^q-acid

> [!CARD] What is multiplicity in a UML class diagram?
> A label on an association end showing how many instances may be linked, e.g. `1`, `0..1`, `*`, `1..*`.
^q-wbsh
