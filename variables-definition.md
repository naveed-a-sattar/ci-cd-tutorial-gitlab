# GitLab CI Variables

This MD file provides a brief overview of GitLab CI variables, including the most basic and core concepts. It also includes example YAML code for each concept.

## What are GitLab CI variables?

Variables are values that can be used in your GitLab CI pipeline. They can be used to store things like environment variables, passwords, or other sensitive data.

## Types of variables

There are two types of variables in GitLab CI:

* **Predefined variables** are variables that are defined by GitLab. They are available to all pipelines, and they can be used without any special configuration.
* **User-defined variables** are variables that are defined by the user. They are only available to the pipelines that they are defined in.

## Defining variables

Variables can be defined at the **root** level of your GitLab CI pipeline, or they can be defined at the **stage** or **job** level.

* **Root-level variables** are available to all stages and jobs in your pipeline.
* **Stage-level variables** are only available to the stages that they are defined in.
* **Job-level variables** are only available to the jobs that they are defined in.

Here is an example of how to define a variable at the root level:

```yaml
variables:
  environment: staging
  password: my-secret-password
```

## Using variables

Variables can be used in your GitLab CI pipeline in a variety of ways. They can be used as parameters to commands, they can be used to set environment variables, and they can be used to store data in files.

Here is an example of how to use a variable as a parameter to a command:

```yaml
before_script:
  - echo "The environment variable is ${environment}"
```

Here is an example of how to use a variable to set an environment variable:

```yaml
env:
  environment: $CI_ENVIRONMENT_SLUG
```

Here is an example of how to use a variable to store data in a file:

```yaml
before_script:
  - echo "The password is ${password}" > my-password.txt
```

## Encrypting variables

Variables can be encrypted in GitLab CI to protect sensitive data. This is done by using the `encrypted` keyword when defining the variable.

Here is an example of how to encrypt a variable:

```yaml
variables:
  encrypted_variable:
    value: my-secret-password
    secret: true
```

I hope this MD file helps you understand the basics of GitLab CI variables.
