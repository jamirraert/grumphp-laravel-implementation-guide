# GrumPHP configuration

```
composer require --dev phpro/grumphp -w
```

### After successfully installing GrumPHP, you will be ask to create a configuration file and add a task, just choose the index number of PhpUnit then press enter.

# <ins>PHP_CodeSniffer</ins>
```
composer require --dev "squizlabs/php_codesniffer=*"
```

#  <ins>PHP Stan</ins> 
## Detect bug before going to production
```
composer require --dev phpstan/phpstan
```

### Basic configuration
```
parameters:
    git_dir: .
    bin_dir: vendor/bin

    # Tasks to be executed by GrumPHP
    tasks:
        # PHPUnit: Runs unit tests before commit
        phpunit:
            always_execute: true  # Always run tests before committing

        # PHP_CodeSniffer: Lint your code for PSR2 compliance
        phpcs:
            standard: PSR2  # Use PSR-2 coding standard
            ignore_patterns:  # Files and directories to ignore (if needed)
                - ./tests/*
                - ./vendor/*
            whitelist_patterns:  # Files and directories to check
                - '/^app\/(.*)/'  # Only check files in the "app" directory
    git_hooks:
        pre_commit: true  
        pre_push: false

```

