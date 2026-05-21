# homo-duix-enterprise — Enterprise security for Duix-Avatar

> Digital watermarking + model encryption + usage audit for Duix-Avatar.  
> Make your digital humans production-ready with enterprise compliance.

## Quick Start

```bash
pip install duix-avatar
pip install homo-duix-enterprise
```

```python
from homo_duix_enterprise import EnterpriseAvatar

# Same API as Duix-Avatar, with added security
avatar = EnterpriseAvatar(
    model_path="./models/my_avatar",
    encrypt_models=True,
    watermark=True,
    audit_log="./audit/usage.log"
)
avatar.generate("Hello, this is my digital twin.")
```

## Why

| Feature | Duix-Avatar | Duix + Enterprise |
|---------|:-----------:|:-----------------:|
| Video watermarking | ❌ None | ✅ Invisible watermark |
| Model encryption | ❌ Plaintext | ✅ AES-256-GCM |
| Usage audit | ❌ None | ✅ Full audit trail |
| Production compliance | ❌ | ✅ Enterprise ready |

## License

MIT - Commercial support available.
