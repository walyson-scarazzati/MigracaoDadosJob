# MigracaoDadosJob
Project from "Curso Otimização de desempenho para jobs Spring Batch" - Udemy: https://www.udemy.com/course/otimizacao-de-desempenho-para-jobs-spring-batch/

This project is a Spring Batch application for migrating data, specifically handling the processing of people and bank data from CSV files. It demonstrates chunk-oriented processing, custom readers, processors, and writers, as well as transaction management with a custom transaction manager.

## Features
- Batch processing with Spring Batch
- Reads data from CSV files (`pessoas.csv`, `dados_bancarios.csv`)
- Custom ItemReader, ItemProcessor, and ItemWriter implementations
- Transaction management
- Configurable chunk size for performance tuning

## Project Structure
- `src/main/java/com/springbatch/migracaodados/` - Main Java source code
- `src/main/resources/` - Configuration files and resources
- `files/` - Input CSV files and SQL scripts

## How to Run
1. Ensure you have Java and Maven installed.
2. Place your input files in the `files/` directory.
3. Configure your database and application settings in `src/main/resources/application.properties`.
4. Start required services with Docker Compose:
   ```sh
   docker compose up -d
   ```
   This will start the services defined in `src/main/resources/docker-compose.yml`.
5. Build the project:
   ```sh
   ./mvnw clean package
   ```
6. Run the application:
   ```sh
   java -jar target/MigracaoDadosJob-<version>.jar
   ```

## Configuration
- Edit `application.properties` for database and batch job settings.
- Adjust chunk size and transaction manager in `MigrarPessoaStepConfig.java` as needed.

## License
This project is for educational purposes.
