# Instructions

1. Make ensure serverless is installed. (npm i -g serverless).
2. Use sls deploy --stage=local for local and according to your stage.
3. Use node according to the runtime of serverless stack.
4. Make serverless.{stage}.functions.yml  & file serverless.{stage}.env.yml accordingly.
5. Use npm init -y and make an index.js file for you lambda function. In that use npm i aws-sdk
6. Use:
        const params = {
            DeliveryStreamName: "test-kinesis-firehose",
            Record: {
                Data: {
                    test: 1,
                    key1: "a",
                    key2: "b"
                }
            }
        };

        const kinesis = new AWS.Firehose({
            region: "us-east-1"
        });

        return await kinesis.putRecord(params).promise();