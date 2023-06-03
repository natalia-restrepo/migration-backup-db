# migration-backup-db

3. Create a feature to backup for each table and save it in the file system in AVRO format.
4. Create a feature to restore a certain table with its backup.

Azure Data factory: df-migration-data-db
Pipelines:  
create_backup_db --> Read from BD: company schema: Company and backup tables into BLOB storage AVRO files
          Parameters: Schema: String:Company
                      list_tables: Array:["jobs","departments","hired_employees"]
                      
restore_backup_db --> Read from Blob storage AVRO files and restore tables BD: company schema: company
          Parameters: Schema: String:Company
                      list_tables: Array:["jobs","departments","hired_employees"]
                      
