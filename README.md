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

Postman: `postman/Auron.postman_collection.json` va `postman/Auron.postman_environment.json`

## Endpointlar

| Method | Path | Auth |
| --- | --- | --- |
| POST | `/auth/login` | yo‘q |
| PATCH | `/auth/update` | superadmin |
| GET | `/categories` | yo‘q |
| GET | `/categories/:id` | yo‘q |
| POST / PATCH / DELETE | `/categories` | token |
| GET | `/products?categoryId=` | yo‘q |
| GET | `/products/search?name=` | yo‘q |
| GET | `/products/:id` | yo‘q |
| POST / PATCH / DELETE | `/products` | token |
| POST | `/contact` | yo‘q → `info@auronlub.com` |
| GET / POST / DELETE | `/upload` | token |
| GET | `/upload/file/:filename` | yo‘q |

Rasmlar `uploads/category`, `uploads/product`, `uploads/files` ga tushadi. Update/delete da eski fayl o‘chadi.

## CORS

`.env` da hozircha `CORS_ORIGIN=*`. Keyin:

```
CORS_ORIGIN=https://auronlub.com,https://www.auronlub.com
```
