# Elastic Beanstalk Notes


# .ebextension files
- JSON or YAML format files located in `.ebextension` folder of your application bundle
- They must bo of `.config` file type and if there are multiple files, **ones that are first alphabetically are first applied**, meaning that they have the lowest precedence priority.