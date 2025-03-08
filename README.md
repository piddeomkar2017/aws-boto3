#setup virtual environment
 python3 -m venv venv
 . venv/Scripts/activate

#install boto3
 pip install boto3

save requirements in requirements.txt
pip freeze > requirements.txt

#to install dependencies
pip install -r requirements.txt 

***************************************
Setting up boto3 to access AWS console
1) aws configure
2) passing credentials as parameters
-> while creating boto3 client
import boto3
client = boto3.client(
    's3',
    aws_access_key_id=ACCESS_KEY,
    aws_secret_access_key=SECRET_KEY,
    aws_session_token=SESSION_TOKEN
)

-> while creating boto3 session
import boto3
session = boto3.Session(
    aws_access_key_id=ACCESS_KEY,
    aws_secret_access_key=SECRET_KEY,
    aws_session_token=SESSION_TOKEN
)


3) Environment variables
* boto3 will check below environment variables for credentials
AWS_ACCESS_KEY_ID - access key of aws account
AWS_SECRET_ACCESS_KEY - secret key of aws account
AWS_SESSION_TOKEN - the sessi0on key of aws account. This is only needed when you are using temprary credentials

4) Via credentials file and config file
~/.aws/credentials