# orderhangnhat-infra

Hạ tầng Docker cho hệ thống order hàng Nhật.

## Dịch vụ
- postgres 16, redis 7, minio, backend (Node), frontend (React static), nginx.
- Chỉ `nginx` expose port 80 ra ngoài; còn lại trong network `internal`.

## Yêu cầu thư mục (clone cạnh nhau)
```
duan-order/
  orderhangnhat-backend/
  orderhangnhat-fronend/
  orderhangnhat-infra/   <- chạy compose ở đây
```

## Chạy
```bash
cp .env.example .env      # sửa secrets
docker compose up -d --build
docker compose exec backend npm run db:deploy   # migrate + seed
```

App: http://APP_DOMAIN/  — API: http://APP_DOMAIN/api/health
