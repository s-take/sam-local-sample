## setup

```
$sudo pip install awscli

$aws configure --profile localstack

AWS Access Key ID [None]: dummy
AWS Secret Access Key [None]: dummy
Default region name [None]: ap-northeast-1
Default output format [None]:
```

```
$pip install -U setuptools
$pip install aws-sam-cli
```

## dynamodb

```
docker-compose up -d
```

create table and insert test data

```
./test/init.sh
```

## invoke lambda

GetUsers

```
$sam local invoke --docker-network xxxx -t template.yaml --event test/get-payload.json --env-vars environments/sam-local.json GetUsers
```

PutUsers

```
$sam local invoke --docker-network xxxx -t template.yaml --event test/put-payload.json --env-vars environments/sam-local.json PutUsers
```
