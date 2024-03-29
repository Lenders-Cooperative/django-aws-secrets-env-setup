# django-aws-secrets-env-setup
This is a helper function to set up environment variables from AWS secrets manager.
The main function to use is `set_env_variables(default_region_name, stop_on_failure=False, **kwargs)`.
In addition to `default_region_name` and `stop_on_failure`, there are several kwargs that can be passed.
#### Parameters
- If `os.environ[region_name_env_name]` is not set, the `default_region_name` will be used as the region name instead.
    - `region_name_env_name` is the name of the environment variable to check for the region name.
        - Default: `'SECRETS_REGION_NAME'`
- `stop_on_failure` is a flag to indicate whether or not errors should be fatal.
    It is strongly recommended for this to be set to True in a production environment. 
- `secrets_name` is the name of the secret to pull secrets from.
    - Default: `os.environ[secrets_name_env_name]'`
        - `secrets_name_env_name` is the name of the environment variable to use if `secrets_name` is not in kwargs.
            - Default: `'SECRETS_NAME'`
- `aws_access_key_id` is the ID of the AWS access key to be used.
    - Default: `os.environ[aws_access_key_id_env_name]'`
        - `aws_access_key_id_env_name` is the name of the environment variable to use if `aws_access_key_id` is not in kwargs.
            - Default: `'AWS_ACCESS_KEY_ID'`
- `aws_secret_access_key` is the AWS key used to access the secrets.
    - Default: `os.environ[aws_secret_access_key_env_name]'`
        - `aws_secret_access_key_env_name` is the name of the environment variable to use if `aws_secret_access_key` is not in kwargs.
            - Default: `'AWS_SECRET_ACCESS_KEY'`
- `service_name` is the service name of the secrets manager to connect to.
    - Default: `'secretsmanager'`
