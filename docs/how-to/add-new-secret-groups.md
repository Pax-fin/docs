# How to: Add a new secret group

Secrets are mastered in Render.

## Steps

1. Go to [environment groups](https://dashboard.render.com/env-groups)
2. Add a new group as needed
    3. Make it environment aware (dev/prod/...)
4. Add k/v secrets as needed
5. With your group name, add to your desired blueprint under `envVars` 
   6. `fromGroup: <new group name>`