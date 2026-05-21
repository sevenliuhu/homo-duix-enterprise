<p align="center">
  <strong>🎭 homo-duix-enterprise</strong>
</p>

<p align="center">
  <em>Digital watermarking + model encryption + usage audit for Duix-Avatar.</em>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  <a href="#"><img src="https://img.shields.io/badge/python-3.8+-green.svg" alt="Python"></a>
  <a href="#"><img src="https://img.shields.io/badge/watermark-steganographic-brightgreen.svg" alt="Watermark"></a>
</p>

---

## Why

Duix-Avatar is a powerful open-source digital human toolkit. But enterprises deploying digital humans face three blockers:

1. **No watermarking** — generated videos can't be traced back to source
2. **No model encryption** — avatar models stored as plaintext, easily stolen
3. **No usage audit** — no record of who generated what content

homo-duix-enterprise adds all three as a thin wrapper around Duix-Avatar.

| Feature | Duix-Avatar | Duix + Enterprise |
|---------|:-----------:|:-----------------:|
| Video watermark | ❌ None | ✅ Invisible steganographic |
| Model encryption | ❌ Plaintext | ✅ AES-256-GCM |
| Usage audit | ❌ None | ✅ JSONL audit trail |
| Production ready | ❌ No | ✅ Yes |

## Quick Start

```bash
pip install duix-avatar
pip install homo-duix-enterprise

export HOMO_DUIX_KEY="your-32-byte-key"
```

```python
from homo_duix_enterprise import EnterpriseAvatar

avatar = EnterpriseAvatar(
    model_path="./models/my_avatar",
    encrypt_models=True,
    watermark=True,
    audit_log="./audit/usage.log"
)
video = avatar.generate("Hello, this is my digital twin.")
# video has invisible watermark + usage is logged
```

## Features

### Digital Watermarking
Invisible steganographic watermark embedded in video frames. Hash of payload + timestamp encoded in least significant bits. Verifiable provenance.

### Model Encryption
Avatar model files encrypted with AES-256-GCM at rest. Decrypted only in memory during generation.

### Usage Audit
Every `generate()`, `encrypt_model()`, and `decrypt_model()` call logged to append-only JSONL file with timestamp and action details.

## License

MIT - Enterprise support at 16208204@qq.com
