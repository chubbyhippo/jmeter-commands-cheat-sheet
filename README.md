# jmeter-commands-cheat-sheet

## Basic Syntax

```shell
jmeter [options]
```

## Run a Test Plan (Non-GUI Mode)

```shell
jmeter -n -t test-plan.jmx
```

- `-n` = non-GUI mode
- `-t` = test plan file

## Save Results to a JTL File

```shell
jmeter -n -t test-plan.jmx -l results.jtl
```

- `-l` = results file

## Generate HTML Report

```shell
jmeter -n -t test-plan.jmx -l results.jtl -e -o report-folder
```

- `-e` = generate HTML dashboard
- `-o` = output folder

## Use Custom Properties File

```shell
jmeter -n -t test-plan.jmx -q custom.properties
```

- `-q` = additional properties file

## Pass JMeter Properties

```shell
jmeter -n -t test-plan.jmx -Jthreads=100 -Jrampup=10 -Jduration=60
```

- `-J` = JMeter property

Example usage inside JMeter:

```shell
${__P(threads)}
${__P(rampup)}
${__P(duration)}
```

## Pass Java System Properties

```shell
jmeter -n -t test-plan.jmx -Dhttp.proxyHost=proxy.example.com -Dhttp.proxyPort=8080
```

- `-D` = Java system property

## Set Log Level

```shell
jmeter -n -t test-plan.jmx -Lorg.apache.jmeter=DEBUG
```

Examples:

```shell
jmeter -n -t test-plan.jmx -LDEBUG
jmeter -n -t test-plan.jmx -Lorg.apache.jmeter.engine=DEBUG
```

## Write Log Output to File

```shell
jmeter -n -t test-plan.jmx -j jmeter.log
```

- `-j` = log file

## Remote / Distributed Testing

Use remote servers from `
