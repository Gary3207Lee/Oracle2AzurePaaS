
# **Oracle2AzurePaaS**

Welcome to the Oracle to Azure PaaS database migration.

</br>

</br>

## **1. Migration Drivers**

- Cost Optimization
- Application & Database Modernization
- Administrative Overhead
- Performance Improvement
- Cloud-First Mindset

![00_01.migration_drivers](./01.MigrationStrategy/Resources/Image/00_01.migration_drivers.png)
</br>

</br>

## **2. Cloud Migration Strategy**

- **Rehost**: Often referred to as “lift and shift” migration, this no-code option lets you migrate your existing applications to Azure quickly. Each application is migrated as-is, which provides the benefits of the cloud without the risks or costs of making code changes, and you can leverage SQL Server on Azure Virtual Machines, Microsoft’s infrastructure as a service (IaaS) product, to achieve that.

- **Refactor**: Often referred to as repackage, this cloud migration strategy involves some change to the application design but no wholesale changes to the application code. Your application can take advantage of infrastructure as a service (IaaS) and platform as a service (PaaS) products, such as Azure App Service, Azure SQL Managed Instance, and containers.

- **Rearchitect**: Modify or extend your application's code base to scale and optimize it for the cloud. Modernize your app into a resilient, highly scalable, independently deployable architecture and use Azure SQL Database, Microsoft’s platform as a service (PaaS) offering, to accelerate the process, scale applications with confidence, and manage your apps with ease.

- **Rebuild**: Rebuild an application from scratch using cloud-native technologies. Azure platform as a service (PaaS) provides a complete development and deployment environment in the cloud, without the expense and complexity of software licenses, the need for underlying application infrastructure, or middleware and other resources. With this cloud migration strategy, you manage the applications and services you develop, and Azure manages everything else.

For more information about cloud migration strategies, see [Start your cloud migration process](https://azure.microsoft.com/en-us/migration/migration-journey/).

</br>

</br>

## **3. Database Migration Process Overview**

![01_01.database_migration_process_overview](./01.MigrationStrategy/Resources/Image/01_01.database_migration_process_overview.png "database_migration_process_overview")
</br>

### **(1) Pre-Migration**

- **Discovery**
  - **What to Discover?**
    - Application Details: Service Target, Service Time, Multi-Tenant, SaaS.
    - Service(Workload) Identity: Dependency for other Apps and Databases.
    - H/W Spec: Cores, IOPS, MEM, Volume.
    - Resource Utilization: Average & Peak resource utilization for CPU, MEM, IOPS, Sessions.
    - Third Party Application
    - Encoding details (UTF 8/16)
    - Database Link details
    - OLTP & OLAP details
    - Custom Field
    - Sharding & Partitioning
    - Performance and Response Time
    - HA & DR details
    - Backup and Retention
    - Sensitive Data details (PII)
    - Compliance Requirement details
    </br>

  - **Outcomes of Discovery**
    - Discover the server, application, and database assets of different sources to Azure SQL Target Databases.
    - Determine application dependencies, database dependencies and available downtime for each business services.
    - Workloads that need to be migrated together (Server, Application, Databases).
    - Inventory collection template filled.
    - Ora2PG / SSMA preliminary inventory details.
    </br>

  - **Accelerators For Discovery**
    - MAP Microsoft Assessment and Planning Toolkit: Inventory, assessment Download Link: [MAP Tool kit](https://www.microsoft.com/en-us/download/details.aspx?id=7826)
    - [Azure Migrate](https://azure.microsoft.com/en-us/products/app-service/migration-tools/) for application workloads and dependencies.
    - [Ora2PG](https://ora2pg.darold.net/) / [SSMA](https://learn.microsoft.com/en-us/sql/ssma/oracle/sql-server-migration-assistant-for-oracle-oracletosql?view=sql-server-ver16) : scans Source Databases and collects schema, Data.
    </br>

- Detailed Guidance for [Oracle to PostgreSQL](./02.Oracle2PostgreSQL/02.Oracle2PostgreSQL.md) Migration Scenario.
- Detailed Guidance for [Oracle to SQL Database](./03.Oracle2SQL/03.Oracle2SQL.md) Migration Scenario.
</br>

</br>

- **Assessment & Convert**
  - **What To Assess**
    - Review and Assess output of Azure migration assistant and Azure Migration output.
    - Assess application technologies and target remediation SKUs, dependency map with application, server, DBs.
    - Run and gather output from Ora2PG / SSMA.
    - Identify Application and Databases breaking and critical changes.
      (For example: Third party application that does not support movement to Azure, functions, Package body and nested procedure calls , Synonyms, Table sub-partitions etc.)
    - Map the discovered inventory with limitations of Azure SQL Database. (For example: Storage -> IOPS)
    - Review LOBS, XML, JSON types.
    - Data load frequency.
    - HA/DR- possible configurations  and cost assessment.
    - Table partitioning,  Indexes, Ingestion record sizes.
    - Realtime analytical workload scenarios.
    - Data Encryption.
    - Experience from previous migration using Ora2PG / SSMA can convert 80-90% schema and 50% of code for very complex code involves nested procedure.
  </br>

  - **Outcomes Of Assessment**
    - Target SKUs (For example: Single Server Vs Hyperscale)
    - Target topology - Application, DB, storage, sizing, network requires, back ups, monitoring, security, logging, analytics, optimization and Modernize options post migration, replication (geo Vs local), back up and retention, storage size, application remediation areas, code changes, function changes/re-write code paths, Deployment and cutover plan.
    - Decision to leave some DBs On-prem and move application only using hybrid connections and move to IaaS for now with a future path to optimize and modernization in the radar i.e. move on to PaaS.
  </br>

  - **Accelerators For Assessment**
    - Application Assessment Azure Migrate
      [Download the Migration Assistant for your .NET and PHP Apps](https://azure.microsoft.com/en-us/products/app-service/migration-tools/).
    - Database Assessment [Ora2PG](https://github.com/darold/ora2pg/releases) / [SSMA](https://www.microsoft.com/en-us/download/details.aspx?id=54258)</br>
      [Ora2PG Docs](https://ora2pg.darold.net/documentation.html) | [SSMA Docs](https://learn.microsoft.com/en-us/sql/ssma/oracle/sql-server-migration-assistant-for-oracle-oracletosql?view=sql-server-ver16)
    - [Migration Guide](https://learn.microsoft.com/en-us/data-migration/) and [Migration Journey and Tools Video](https://learn.microsoft.com/en-us/shows/data-exposed/?terms=oracle)
  </br>

- Detailed Guidance for [Oracle to PostgreSQL](./02.Oracle2PostgreSQL/02.Oracle2PostgreSQL.md) Migration Scenario.
- Detailed Guidance for [Oracle to SQL Database](./03.Oracle2SQL/03.Oracle2SQL.md) Migration Scenario.
</br>

</br>

### **(2) Migration**

- Detailed Guidance for [Oracle to PostgreSQL](./02.Oracle2PostgreSQL/02.Oracle2PostgreSQL.md) Migration Scenario.
- Detailed Guidance for [Oracle to SQL Database](./03.Oracle2SQL/03.Oracle2SQL.md) Migration Scenario.
</br>

</br>

### **(3) Post-Migration**

After migration it is important to use an iterative optimization process to ensure the best performance and functionality of your solution in the target environment

- **Verification**:
  - Verify the schema and data.
  - Application connectivity and post migration remediations.
- **Optimization Opportunities**:
  - Optimize with configuration changes identified during Assessment phase and look for key indicators.
  - Look for resource contention.
  - Check database performance.
- Use [Azure Advisor](https://azure.microsoft.com/en-us/products/advisor/#overview) for Azure deployments.
- Look for performance stats:
  - [Tune applications and databases for performance in Azure SQL Database and Azure SQL Managed Instance](https://learn.microsoft.com/en-us/azure/azure-sql/database/performance-guidance?view=azuresql).
  - [Perform intelligent tuning in Azure Database for PostgreSQL](https://learn.microsoft.com/en-us/azure/postgresql/flexible-server/concepts-intelligent-tuning).
</br>

</br>

## **4. Hands On Lab**

- Hands On Lab Exercise for [Oracle to PostgreSQL](./02.Oracle2PostgreSQL/02.Oracle2PostgreSQL_HoL.md) Migration Scenario.
- Hands On Lab Exercise for [Oracle to SQL Database](./03.Oracle2SQL/03.Oracle2SQL_HoL.md) Migration Scenario.

</br>

</br>

## **5. Multi-Tenant Architecture (SaaS Database Architecture)**

</br>

</br>

# **Learning Path**

</br>

</br>

# **Other Resources**

</br>

</br>

# **Contribution**

Welcomes for contributions and suggestions.
