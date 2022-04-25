1

docker run -v "$PWD":/var/task "lambci/lambda:build-python3.7" /bin/sh -c "yum install -y postgresql-devel python-psycopg2 postgresql-libs gcc g++ build essential python3-dev libpq-dev psycopg2; pip install -r requirements.txt -t python/lib/python3.7/site-packages/; exit"

2

aws lambda publish-layer-version --layer-name reviews_lambda_layer --description "My python libs for reviews lambda app" --zip-file fileb://reviews_lambda_layer.zip --compatible-runtimes "python3.7" --profile pub --region eu-west-1
