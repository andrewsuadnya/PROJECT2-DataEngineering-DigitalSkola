# Download Potgresql
https://www.enterprisedb.com/download-postgresql-binaries

# Using Docker
1. Download and install [docker](https://docs.docker.com/desktop/install/windows-install/) and [docker-compose](https://docs.docker.com/compose/install/)
2. Run `docker-compose up -d`


![Alt text](image.png)


1. Turn on Postgresql database service
2. Open DBeaver and connect to Postgresql database
2. Open `transactions_dw.sql`
3. Run all DDLs

# ======= DBT Installation Part (Windows) =======
1. Create your project directory
2. Run `pip install virtualenv` in Shell CMD
3. In Shell run `cd my-project`
4. Run `virtualenv --python C:\Path\To\Python\python.exe env`
5. Activate `.\env\Scripts\activate`
4. Install DBT `pip install dbt-core==1.7.0 dbt-postgres==1.7.0`

# ============ DBT Setup Part ============ 
1. Change your terminal directory to your project directory
2. Initialize DBT project `dbt init`
3. To validate connection change directory to the root project and run `dbt debug`
4. Run your first model `dbt run -s my_first_dbt_model`
5. If database not found don't forget to create it first using `CREATE DATABASE <DB_NAME>;`
6. Setup profiles.yml https://docs.getdbt.com/docs/core/connect-data-platform/snowflake-setup
7. Setup sources https://docs.getdbt.com/docs/build/sources
8. Once the model was ran open dbt UI `dbt docs generate` then run `dbt docs serve`


# ======== BUILD DATA WAREHOUSE =========
1. Change directory to `dbt_project`
2. Create `intermediete` directory inside `models` directory:
   - Create `dim_customer.sql`
   - Create `dim_time.sql`
   - Create `dim_product.sql`
   - Create `fact_sales.sql`
3. Create `mart` directory inside `models` directory:
   - Create `mart_revenue_monthly.sql`
4. Run this command in the terminal to build model `dbt run`
5. Run this command to generate DBT documentation `dbt docs generate`
6. Run this command to generate DBT UI `dbt docs serve --port 8080` 


