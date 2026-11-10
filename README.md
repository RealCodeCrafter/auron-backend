# Auron backend

Winner backend bilan bir xil tizim. NestJS + TypeORM + PostgreSQL.

Domen: `auronlub.com`  
Contact pochta: `info@auronlub.com`

## Ishga tushirish

```bash
cd auron-backend
copy .env.example .env
npm install
npm run start:dev
```

Yoki `install.bat`.

PostgreSQL da `database/init.sql` ni ishga tushiring, keyin `superadmin` jadvaliga bcrypt hash bilan login yozing.

## API

Global prefix: `/api`

| Method | Path | Auth |
| --- | --- | --- |
| POST | `/api/auth/login` | yo‘q |
| PATCH | `/api/auth/update` | superadmin |
| GET | `/api/categories` | yo‘q |
| GET | `/api/categories/:id` | yo‘q |
| POST / PATCH / DELETE | `/api/categories` | token |
| GET | `/api/products?categoryId=` | yo‘q |
| GET | `/api/products/search?name=` | yo‘q |
| GET | `/api/products/:id` | yo‘q |
| POST / PATCH / DELETE | `/api/products` | token |
| POST | `/api/contact` | yo‘q → `info@auronlub.com` |
| GET / POST / DELETE | `/api/upload` | token |
| GET | `/api/upload/file/:filename` | yo‘q |

Rasmlar `uploads/category`, `uploads/product`, `uploads/files` ga tushadi. Update/delete da eski fayl o‘chadi.

## CORS

`.env` da hozircha `CORS_ORIGIN=*`. Keyin:

```
CORS_ORIGIN=https://auronlub.com,https://www.auronlub.com
```
