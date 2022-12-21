# aws-cloudformation-templates
AWS Cloudformation basic definitions & templates

# Basic CLI commands

## Create Stack

aws cloudformation create-stack --stack-name simple-cf-stack --template-body file://SimpleTemplate.yaml

## Update Stack

aws cloudformation update-stack --stack-name simple-cf-stack --template-body file://SimpleTemplate.yaml

## Create Change Set

aws cloudformation create-change-set --stack-name simple-cf-stack --change-set-name example-change-set --template-body file://ChangeSets.yaml

## Display Change Set

aws cloudformation describe-change-set --stack-name simple-cf-stack --change-set-name example-change-set

## Execute Change Set

aws cloudformation execute-change-set --stack-name simple-cf-stack --change-set-name example-change-set

## Delete Change Set

aws cloudformation delete-change-set --stack-name simple-cf-stack --change-set-name example-change-set

## Delete Stack

aws cloudformation delete-stack --stack-name simple-cf-stack

# Definitions

### * Intrinsic functions
- built-in functions that help you manage your stacks

Fn::Join appends a set of values into a single value

Example: !Join [delimeter, [comma-delimited list of values]]

    !Join [ ":" ,  [a, b, c] ] --> "a:b:c"


### * Multiple resources

- You can define dependencies among multiple resources in your templates

- You can use Ref intrinsic function to refer to dependency


### * Pseudo Parameters

- Parameters that are predefined by cloudformation
- similar to environment variables
- reference the parameters using Ref intrinsic function

Some Pseudo parameters

AWS::AccountId -> returns AWS account ID of the account
AWS::NotificationARNs -> returns list of notification ARNs for current stack
AWS::StackId -> returns ID of stack
AWS::StackName -> return name of stack
AWS::Region -> returns a string representing AWS region in which the resource is being created

### * Mappings

- They enable us to use an input value to determine another value

### * Input Parameters

- They enable us to input custom values to our templates.
- They are defined within the top level Parameters section.
- Each parameter must be assigned a value at runtime. You can optionally specify a default value.
- The only required attribute is Type which is the data type.

Supported Parameter Types:
String
Number
List<Number>
CommaDelimitedList
AWS-specific types (AWS::EC2::Image::Id)
System Manager Parameter types


### *  Outputs

- They enable us to get access to information about resources within stack


### * Change Sets

- They allow us to preview how changes will impact to our resources

Four operations of a change set

Create: create a change set for an existing stack by submitting a modified template. This does not modify existing stack.

View: after creating, you can view proposed changes.
 
Execute: executing a change set updates the changes on existing stack

Delete: you can delete a change set without performing the changes