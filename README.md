# node-lambda
Command line tool to locally run and deploy your node.js application to [Amazon Lambda](http://aws.amazon.com/lambda/).


Forked from node-lambda
Original work [here](https://travis-ci.org/motdotla/node-lambda)


```
lambda run
```

## Installation

```
npm install -g aws-lambda
```

## Example App

The [node-lambda-template](https://github.com/RebelMail/node-lambda-template) example app makes it easy to get up and running.

## Usage

There are 3 available commands.

```
node-lambda setup
node-lambda run
node-lambda deploy
```

### Commands

#### setup

Initializes the `event.json` and `.env` files. `event.json` is where you mock your event. `.env.` is where you place your deployment configuration.

```
$ node-lambda setup --help

  Usage: run [options]

  Options:

    -h, --help                     output usage information
```

After running setup, it's a good idea to gitignore the generated `event.json` and `.env` file.

```
echo ".env\nevent.json" >> .gitignore
```

#### run

Runs your Amazon Lambda index.js file locally. Passes `event.json` data to the Amazon Lambda event object.

```
$ node-lambda run --help

  Usage: run [options]

  Options:

    -h, --help                     output usage information
    -h, --handler [index.handler]  Lambda Handler {index.handler}
```

#### deploy

Bundles and deploys your application up to Amazon Lambda.

```
$ node-lambda deploy --help

  Usage: deploy [options]

  Options:

    -h, --help                        output usage information
    -e, --environment [staging]       Choose environment {development, stating, production}
    -a, --accessKey [your_key]        AWS Access Key
    -s, --secretKey [your_secret]     AWS Secret Key
    -r, --region [us-east-1]          AWS Region
    -n, --functionName [node-lambda]  Lambda FunctionName
    -h, --handler [index.handler]     Lambda Handler {index.handler}
    -m, --mode [event]                Lambda Mode
    -o, --role [your_role]            Amazon role
    -m, --memorySize [128]            Lambda Memory Size
    -t, --timeout [3]                 Lambda Timeout
    -d, --description [missing]       Lambda Description
    -u, --runtime [nodejs]            Lambda Runtime
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Running tests

```
npm install
npm test
```
