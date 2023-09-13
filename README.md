# AWS CloudFormation Custom Resource Handling with Python's `cfnresponse` Package

The `cfnresponse` package is a Python module tailored for streamlining custom resource management in AWS CloudFormation, especially within AWS Lambda environments. This package empowers developers to create, update, and delete custom resources seamlessly using Lambda functions.

## Practical Use

Designed primarily for AWS Lambda functions serving as custom resource handlers in CloudFormation stacks, the `cfnresponse` package extends CloudFormation's capabilities by enabling the execution of custom logic during stack creation, updates, or deletions.

For detailed examples showcasing how to leverage the `cfnresponse` package, you can explore the [samples](https://github.com/ggiallo28/cfnresponse/tree/907255318ae6bea3729818036c20c323f5790952/samples) directory in this repository. Each sample demonstrates various scenarios of custom resource handling within CloudFormation.

## Repository Structure

The project repository is structured as follows:

- `cfnresponse`: Houses the `__init__.py` file, providing the core `cfnresponse` module.
- `LICENSE`: Contains licensing information pertinent to the package.
- `README.md`: The very document you are reading, offering essential usage instructions.
- `samples`: Comprises sample Lambda functions that exemplify practical `cfnresponse` usage (actual code is found in the repository, not within this README).
- `setup.py`: Configuration file for setting up the package.
- `tests`: Encompasses test cases tailored for evaluating the `cfnresponse` package's functionality.

## Important Note

This package maintains backward compatibility with Amazon Web Services (AWS) cfnresponse module, which is available within Python AWS Lambda environments. If you wish to compare the code in this package with the original, you can do so with the following commands:

```bash
if [ "$(curl -s https://raw.githubusercontent.com/awslabs/aws-cloudformation-templates/master/aws/services/CloudFormation/MacrosExamples/StackMetrics/lambda/cfnresponse.py | sha256sum)" = "$(curl -s https://raw.githubusercontent.com/gene1wood/cfnresponse/master/cfnresponse/__init__.py | sha256sum)" ]; then
    echo "GitHub version matches AWS version";
fi

if [ "$(curl -s https://raw.githubusercontent.com/awslabs/aws-cloudformation-templates/master/aws/services/CloudFormation/MacrosExamples/StackMetrics/lambda/cfnresponse.py | sha256sum)" = "$(wget --quiet https://files.pythonhosted.org/packages/03/69/2d3fafdf434a0d8ef62a5c1fa09feda25b31fad4db20c54ed067054f9b95/cfnresponse-1.1.2-py2.py3-none-any.whl && unzip -p cfnresponse-1.1.2-py2.py3-none-any.whl cfnresponse/__init__.py | sha256sum && rm cfnresponse-1.1.2-py2.py3-none-any.whl)" ]; then
    echo "PyPI version matches AWS version";
fi
```
