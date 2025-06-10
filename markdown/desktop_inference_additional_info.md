# Run Inference on the Desktop

## Managing CSV file reading settings

When a CSV file is used as a dataset, you can specify the delimiter character, the name of the target column and the name of the session column if they differ from the default values \`,\` and \`target\`, \`session\` respectively. This can be done by specifying additional parameters when calling \``inference`\` and \``metrics`\` command.

Use "-d <delimiter>" or "--delimiter <delimiter>" to specify delimiter character by keywords:

* comma - \`,\`
* semicolon - \`;\`
* tab - \`\\t\`
* caret - \`^\`
* vbar - \`\|\`

```
.\artifacts\inference_runner>neuton_inference_runner_linux inference test.csv -d tab
```

Use "-t <target name>" or "--target <target name>" to specify the target column name of the provided dataset.

```
.\artifacts\inference_runner>neuton_inference_runner_linux inference test.csv -t label
```

Use "-sn <session name>" or "--session <session name>" to specify the session column name of the provided dataset.

```
.\artifacts\inference_runner>neuton_inference_runner_linux inference test.csv -sn testee
```