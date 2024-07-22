# prisma-cockroachdb-region-enum

```bash
# regions rely on an enterprise licence (trial licences should work)
export COCKROACH_ORG='...'
export COCKROACH_LICENSE_KEY='...'

docker compose up -d

export DATABASE_URL='postgresql://root@localhost:26257/example?sslmode=disable'

cockroach sql --url "$DATABASE_URL" -e '
    ALTER DATABASE example PRIMARY REGION "aws-us-east-1";
    ALTER DATABASE example ADD REGION "aws-us-west-2";
'

npx prisma db pull

npx prisma migrate dev
```
