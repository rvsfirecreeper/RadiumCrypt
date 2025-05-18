# RadiumCrypt

> "Why reinvent the wheel when you can slap a 7000-horsepower quantum-resistant engine on it?"

RadiumCrypt is an experimental post-quantum-ready encryption framework that wraps tried-and-true block ciphers in a novel, segment-based key chaining system. Built for future-proofing, paranoid infosec nerds, and hackers with GPUs to spare.

---

## Features

- **Segmented Block Chaining:**  
  Decryption is *sequentially enforced*; each block's key depends on previous decrypted plaintexts.  
  Segments reset every N blocks (configurable), allowing **controlled parallelism** for performance without letting GPUs slice the security like butter.

- **Cascade-Ready Cipher Stacks:**  
  Choose from AES-256, Twofish, Camellia, Serpent.  
  Cascade them in any order (or stack all four, go nuts).  
  Future-friendly: easily swap in post-quantum ciphers when available.

- **Header Metadata:**  
  JSON-based with magic bytes (`0x52 0x43 0x59 0x50`)  
  Includes versioning, segment size, cipher suite, flags, and HMACs.

- **Padding & Integrity:**  
  PKCS#7 padding.  
  HMAC-SHA-512 per segment or global (depending on file type).

- **Zero reinventing:**  
  All crypto is standard, hardened, and audited. RadiumCrypt just handles the logic scaffolding.

---
> For information on frontend development, cryptographic details, and more, please read the [Wiki](Home)
## Why?

Quantum computers are coming. A lot of people pretend AES-only is fine. It’s not. RadiumCrypt doesn’t replace AES, I believe that's unnecessary. It **amplifies** it by wrapping it in a structure that resists parallelism and other modern vulnerabilities.

---

## Project Status

| Stage        | Description                                   |
|--------------|-----------------------------------------------|
| `Alpha`      | Backend concept validation, no CLI yet        |
| `Beta`       | CLI with encryption/decryption support        |
| `Stable`     | Full-disk encryption (FDE), offshore header backup, segment tuning |

> Current Stage: Alpha

---

## Planned Features

- [ ] Segment chaining logic  
- [ ] Header HMAC integrity checking  
- [ ] CLI wrapper with KDF support  
- [ ] Full-disk encryption (FDE) mode  
- [ ] Container-based VeraCrypt-style operation  
- [ ] Auto-updating header backup export  

---

## WARNING

RadiumCrypt is **NOT READY FOR PRODUCTION**. Do **NOT** use it for anything critical or outside a VM environment until it’s battle-tested.

---

## Philosophy

- **Not reinventing the wheel.** Just giving it claws.  
- **Make crypto modular.** Let users pick, swap, and configure.  
- **Be quantum-aware, not quantum-paralyzed.**  
- **Let the nerds build it now, let the quantum devs port it later.**

---
## License

MIT. Open to community input. FOSS is peak.

---

For more information, please read the [Wiki](../../wiki)
