# How to: Access Postgresl

In a breakglass situation, you may want to run sql queries against your database directly.

## Steps

1. ensure you have a pg client available
    2. [download pgadmin](https://www.postgresql.org/download/)
    3. `brew search postgres`
4. Open up the whitelist in Render in the database info tab
    5. [Example: dev database](https://dashboard.render.com/d/dpg-clhbqtl8td7s73bnk8f0-a/info)
    6. Under Access Control add **source**
7. Then you can pull your connection details from the **PSQL Command** text box
8. Connect through your preferred client