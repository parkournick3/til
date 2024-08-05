## Validating .env file with zod

I don't know why people don't use it 🤪

```typescript
// env.ts
import 'dotenv/config'
import { z } from 'zod'

const envSchema = z.object({
  NODE_ENV: z
    .enum(['development', 'test', 'production'])
    .default('development'),
  DATABASE_URL: z.string(),
  PORT: z.coerce.number().default(3333),
})

const _env = envSchema.safeParse(process.env)

// handle errors
if (_env.success === false) {
  console.error('⚠️ Invalid environment variables!', _env.error.format())

  throw new Error('Invalid environment variables.')
}

export const env = _env.data

// Usage example
// server.ts
app
  .listen({
    port: env.PORT,
  })
  .then(() => {
    console.log(`server running on port ${env.PORT}`)
  })

```
