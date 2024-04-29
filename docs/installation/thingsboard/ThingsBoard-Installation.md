## Ubuntu Server using Java
This guide describes how to install ThingsBoard on Ubuntu 18.04 LTS / Ubuntu 20.04 LTS. Hardware requirements depend on chosen database and amount of devices connected to the system. To run ThingsBoard and PostgreSQL on a single machine you will need at least 1Gb of RAM. To run ThingsBoard and Cassandra on a single machine you will need at least 8Gb of RAM.

### Step 1. Install Java 11 (OpenJDK)
ThingsBoard service is running on Java 11. Follow this instructions to install OpenJDK 11:

```bash script
sudo apt update
sudo apt install openjdk-11-jdk
```

Don't forget to configure your operating system to use OpenJDK 11 by default. You can configure which version is the default using the following command:

```bash script
sudo update-alternatives --config java

# Check the installation version using this command
java -version
```

Expected command output is:
```bash script
openjdk version "11.0.xx"
OpenJDK Runtime Environment (...)
OpenJDK 64-Bit Server VM (build ...)
```

### Step 2. ThingsBoard service installation

Download and install the thingsboard package using these commands:

```bash script
# Download the installation package
wget https://github.com/thingsboard/thingsboard/releases/download/v3.6.2/thingsboard-3.6.2.deb

# Install TB as a service
sudo dpkg -i thingsboard-3.6.2.deb
```

### Step 3. Configure ThingsBoard database
ThingsBoard is able to use SQL or hybrid database approach. But in our case, we use PostgreSQL because it's recommended for development and production environments with reasonable load. This method is a cost-effective solution for most of ThingsBoard instances.

We need to install **PostgreSQL** using these commands:
```bash script
# install **wget** if not already installed:
sudo apt install -y wget

# import the repository signing key:
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

# add repository contents to your system:
echo "deb https://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" | sudo tee  /etc/apt/sources.list.d/pgdg.list

# install and launch the postgresql service:
sudo apt update
sudo apt -y install postgresql-15
sudo service postgresql start
```

Once PostgreSQL is installed you may want to create a new user or set the password for the the main user. The instructions below will help to set the password for main postgresql user

```bash script
stgres
psql
\password
\q
```

Then, press “Ctrl+D” to return to main user console and connect to the database to create thingsboard DB:

```bash script
psql -U postgres -d postgres -h 127.0.0.1 -W
CREATE DATABASE thingsboard;
\q
```

Next, you must edit ThingsBoard configuration file with this command:
```bash script
sudo nano /etc/thingsboard/conf/thingsboard.conf
```

Add the following lines to the configuration file. Don’t forget **to replace** “PUT_YOUR_POSTGRESQL_PASSWORD_HERE” with your **real postgres user password**:

``` bash script
# DB Configuration 
export DATABASE_TS_TYPE=sql
export SPRING_DATASOURCE_URL=jdbc:postgresql://localhost:5432/thingsboard
export SPRING_DATASOURCE_USERNAME=postgres
export SPRING_DATASOURCE_PASSWORD=PUT_YOUR_POSTGRESQL_PASSWORD_HERE

# Specify partitioning size for timestamp key-value storage. Allowed values: DAYS, MONTHS, YEARS, INDEFINITE.
export SQL_POSTGRES_TS_KV_PARTITIONING=MONTHS
```

### Step 4. Choose ThingsBoard queue service
ThingsBoard is able to use various messaging systems/brokers for storing the messages and communication between ThingsBoard services. How to choose the right queue implementation?

- In Memory queue implementation is built-in and default. It is useful for development(PoC) environments and is not suitable for production deployments or any sort of cluster deployments. **In Memory queue is built-in and enabled by default. No additional configuration steps required.**

- Kafka is recommended for production deployments. This queue is used on the most of ThingsBoard production environments now. It is useful for both on-prem and private cloud deployments. It is also useful if you like to stay independent from your cloud provider. However, some providers also have managed services for Kafka. See AWS MSK for example.

- RabbitMQ is recommended if you don’t have much load and you already have experience with this messaging system.

- AWS SQS is a fully managed message queuing service from AWS. Useful if you plan to deploy ThingsBoard on AWS.

- Google Pub/Sub is a fully managed message queuing service from Google. Useful if you plan to deploy ThingsBoard on Google Cloud.

- Azure Service Bus is a fully managed message queuing service from Azure. Useful if you plan to deploy ThingsBoard on Azure.

- Confluent Cloud is a fully managed streaming platform based on Kafka. Useful for a cloud agnostic deployments.
