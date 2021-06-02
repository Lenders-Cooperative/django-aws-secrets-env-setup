# django-aws-secrets-env-setup
This is a helper function to set up environment variables from AWS secrets manager.
The main function to use is `set_env_variables(default_region_name, **kwargs)`.
In addition to `default_region_name`, there are several kwargs that can be passed.
#### Parameters
- If the `os.environ['SECRETS_REGION_NAME']` is not set, the `default_region_name` will be used as the `region_name` instead.
- `secrets_name` is the name of the secret to pull secrets from. Default: `os.environ['SECRETS_NAME']'`
- `aws_access_key_id` is the ID of the AWS access key to be used. Default: `os.environ['AWS_ACCESS_KEY_ID']'`
- `aws_secret_access_key` is the AWS key used to access the secrets. Default: `os.environ['AWS_SECRET_ACCESS_KEY']'`
- `service_name` is the service name of the secrets manager to connect to. Default: `'secretsmanager'`
