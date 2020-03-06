# func-cicd-pipeline-cfn-template
CloudFormation nested-stack templates for generic Python Lambda functions (i.e. making calls to an API) with its source code in Github.

## Prerequisites

- Put yaml files in some S3 bucket **in the same region** as you want your resources be created in.

- Create a repo for your function source-code. An example can be found here: https://github.com/vahdet/python-lambda-template/

- [Create](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line#creating-a-token) and note down a Github personal access token: we will use it for `GitHubOAuthToken`. The token should have scopes:

- repo
- repo:status
- admin:repo_hook

## Development Notes

### Creating a repository for the function source code

See https://docs.aws.amazon.com/lambda/latest/dg/build-pipeline.html#setup-repository

### Testing validity of templates 

Having AWS CLI installed the following command can be run for a file.

```
aws cloudformation validate-template --template-body file://{yaml_file_name}
```

## References

- [CodePipeline Action Configuration keys](https://docs.aws.amazon.com/codepipeline/latest/userguide/reference-pipeline-structure.html#structure-configuration-examples)

- [Access Tokens for Code Build](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-access-tokens.html)