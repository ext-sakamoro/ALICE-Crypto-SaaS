# ALICE-Crypto SaaS

Information-theoretic security primitives API

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Crypto |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/encrypt` | データ暗号化（XChaCha20-Poly1305） |
| `POST /api/v1/decrypt` | データ復号 |
| `POST /api/v1/hash` | BLAKE3ハッシュ計算 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
