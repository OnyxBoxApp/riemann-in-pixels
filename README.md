<p align="center"><img src="proof.png" alt="175,187 points of light" width="100%"></p>

<h1 align="center">175,187</h1>
<p align="center"><b>The Riemann hypothesis proof, in pixels.</b><br>
1 GB of machine-written Lean · one picture · every piece checks back byte for byte</p>

<p align="center">
<a href="https://github.com/OnyxBoxApp/riemann-in-pixels/releases/tag/v1"><b>Download the picture</b></a> ·
<a href="https://onyxsafebox.com/175187">See it on the web</a> ·
<a href="https://apps.apple.com/us/app/onyx-box/id6798628929">Onyx Box on the App Store</a>
</p>

---

That's not noise up there.

On November 20th a proof of the Riemann hypothesis showed up: written by a machine, checked by
a machine, a quarter of a million pages of it. A gigabyte of Lean nobody will ever read.

I didn't read it either.

I looked at it.

Every square in that picture is one file of the proof. Every one of them is real, and every
one of them still answers to the original, byte for byte. Brighter means more of the proof
is standing on it. The blue ones repeat themselves. There are no red ones.

There was supposed to be red.

## What we found

| | |
|---|---|
| files | **175,187** |
| lines | **17,374,215** |
| declarations | **1,066,087** (784k theorems) |
| `sorry` · `admit` · homemade `axiom` · `native_decide` · `unsafe` | **0 · 0 · 0 · 0 · 0** |
| bodies that are exact copies of another | **~3%** |
| files nothing depends on | **1**, the theorem itself |
| the stone everything rests on | `RhoDetPrimeEqMuTildeMulChiPow` |
| where the weight sits | 41% in the abelian-variety theory |

It has changed twice since it was released. This is the first one, pinned to
[`40e56ba`](https://github.com/leanprover-community/riemann-hypothesis/tree/40e56bab026552e089d7afcfeff08d2defb9c005),
which matches the official tarball's sha256 exactly.

## The picture is not just a picture

[`RIEMANN_PROOF_IN_PIXELS.lcarspic.png`](https://github.com/OnyxBoxApp/riemann-in-pixels/releases/tag/v1)
opens as an image anywhere.

Open it another way and it remembers what it is: the whole map. Every file's name, its
fingerprint, what it leans on, what leans on it, and how much of the proof rests on it.
Ask it for any piece and that piece comes home from where it lives, and proves it's the same
one that left.

58 MB of picture. One gigabyte of proof. None of the proof is actually in it.

Don't take my word for it:

```bash
file RIEMANN_PROOF_IN_PIXELS.lcarspic.png
unzip -l RIEMANN_PROOF_IN_PIXELS.lcarspic.png
```

```bash
unzip -p RIEMANN_PROOF_IN_PIXELS.lcarspic.png atoms.jsonl.gz | gunzip | grep -m1 '"lean/src/Main.lean"'
```

```bash
curl -s https://raw.githubusercontent.com/leanprover-community/riemann-hypothesis/40e56bab026552e089d7afcfeff08d2defb9c005/src/Main.lean | shasum -a 256
```

The last two print the same fingerprint, `017645ca…0939`. Pick any other file and do the
same. We did it with eight at random. Eight for eight.

```
picture  sha256  910e018e2877fcdf68807592d6e64fcefcde624f6a462e4cea32892cfa469c9e
```

## For the AI people

A model wrote 17 million lines of math and a kernel signed off on all of it. Nobody can read
that. So stop trying to read it and start **mapping** it.

- **The weight is in the pixel.** Each square's brightness is a settled importance score over
  753,000 import edges. That's a weight, and the picture *is* the weight map.
- **The content stays where it lives.** The picture carries addresses and fingerprints, not
  text. You pull the one piece you need, when you need it, and it proves itself on arrival.
- **It runs on a laptop.** 23 minutes to stream and map the whole thing, under 1 GB of RAM,
  no GPU, nothing downloaded to disk but the map.

Now picture the same trick on things that aren't proofs.

## What this is not

- **Not our proof.** It belongs to the people and the machine who made it:
  [the official release](https://alpo.ge) · [the mirror](https://github.com/leanprover-community/riemann-hypothesis).
- **Not a verdict on whether it's right.** MIT's [independent check](https://math.mit.edu/~drew/grh/)
  is the one that compiled it. We counted, we mapped, and we kept the receipts.
- **Not a copy.** The map holds names, fingerprints and wiring. The words stay where they live.

## Why

Because a file should know what it is, and tell you where the rest of it went.

That's the whole idea behind **[Onyx Box](https://onyxsafebox.com)**. Your photos and videos get
sealed on your own phone with a fingerprint of the exact bytes. They carry almost nothing, and they
can always tell you if they've changed. No ads, and your originals never leave your phone.

**[Get it on the App Store](https://apps.apple.com/us/app/onyx-box/id6798628929)** · **[onyxsafebox.com](https://onyxsafebox.com)**

## Who made this

**TJ Bell**, BellTone Labs. Self-taught physicist, C++ and Rust engineer. Network security and APIs
for DirecTV. Three years building American Airlines terminal wayfinding. Guarded credit-card
servers through PCI audits. 25 years as the one in the room when half the internet went down.

This was a fun night.

— TJ
