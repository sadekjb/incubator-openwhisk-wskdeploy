# ```wskdeploy``` utility by example
_A step-by-step guide for deploying Apache OpenWhisk applications using Package Manifest files._

This guide will walk you through how to describe OpenWhisk applications using the [OpenWhisk Packaging Specification](https://github.com/apache/incubator-openwhisk-wskdeploy/tree/master/specification) and deploy them through the Whisk Deploy utility.

### Setting up your Host and Credentials
In order to deply your OpenWhisk package, at minimum, the wskdeploy utility needs valid OpenWhisk APIHOST and AUTH variable to attempt deployment. Please read the [Configuring wskdeploy](wskdeploy_configuring.md)

# Debugging your package
In addition to the normal output the wskdeploy utility provides, you may enable additional information that may further assist you in debugging. Please read the [Debugging Whisk Deploy](wskdeploy_debugging.md) document.

# Creating a "hello world" application

As with most language introductions, here we show a minimal "hello world" application as encoded in an OpenWhisk Package Manifest YAML file:

```
helloworld:
  version: 1.0
  license: Apache-2.0
  actions:
    hello:
      version: 1.0
      function: src/hello/hello.js
```

where "hello.js" contains the following JavaScript code:
```
function main(params) {
    console.log('hello', params.payload+'!');
    return { payload:  msg };
}
```

## Creating a valid Package

The "hello world" example, however, does not represent the minimum valid Manifest file which would need to include only the required parts of the Package desciptor.

Please see [wskdeploy_packages.md](wskdeploy_packages.md) for an exploration of the **Packages** schema.
