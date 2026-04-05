# Deploy mockup lên Vercel

## Cách nhanh (CLI)

```bash
npm i -g vercel
vercel login
vercel --prod
```

## Cách qua web dashboard

1. Push branch lên GitHub.
2. Vào Vercel dashboard > **Add New Project**.
3. Import repository này.
4. **Root Directory phải là `/`** (không chọn thư mục con).
5. Framework Preset: **Other**.
6. Build Command: để trống.
7. Output Directory: để trống.
8. Deploy.

## Fix lỗi 404 sau deploy

Nếu domain trả về 404 (kể cả `/`), kiểm tra:

- Project đang deploy đúng branch có file `index.html` ở repo root.
- Root Directory không bị đặt nhầm vào thư mục không có `index.html`.
- `vercel.json` đã có `builds` + `routes` để luôn trỏ về `index.html`.

Sau khi chỉnh, bấm **Redeploy** (clear build cache nếu cần).

## File phục vụ deploy

- `index.html`: landing page mockup.
- `vercel.json`: ép Vercel build static + route toàn bộ request về `index.html`.
