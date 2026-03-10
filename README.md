# jmeter-commands-cheat-sheet

## Basic Syntax

`jmeter [options]`

## Run a Test Plan (Non-GUI Mode)

`jmeter -n -t test-plan.jmx`

- `-n` = non-GUI mode
- `-t` = test plan file

## Save Results to a JTL File

`jmeter -n -t test-plan.jmx -l results.jtl`

- `-l` = results file

## Generate HTML Report

`jmeter -n -t test-plan.jmx -l results.jtl -e -o report-folder`

- `-e` = generate HTML dashboard
- `-o` = output folder

## Use Custom Properties File

`jmeter -n -t test-plan.jmx -q custom.properties`

- `-q` = additional properties file

## Pass JMeter Properties

`jmeter -n -t test-plan.jmx -Jthreads=100 -Jrampup=10 -Jduration=60`

- `-J` = JMeter property

Example usage inside JMeter:

`${__P(threads)}`
`${__P(rampup)}`
`${__P(duration)}`

## Pass Java System Properties

`jmeter -n -t test-plan.jmx -Dhttp.proxyHost=proxy.example.com -Dhttp.proxyPort=8080`

- `-D` = Java system property

## Set Log Level

`jmeter -n -t test-plan.jmx -Lorg.apache.jmeter=DEBUG`

Examples:

`jmeter -n -t test-plan.jmx -LDEBUG`
`jmeter -n -t test-plan.jmx -Lorg.apache.jmeter.engine=DEBUG`

## Write Log Output to File

`jmeter -n -t test-plan.jmx -j jmeter.log`

- `-j` = log file

## Remote / Distributed Testing

Use remote servers from `jmeter.properties`:

`jmeter -n -t test-plan.jmx -r`

Use specific remote servers:

`jmeter -n -t test-plan.jmx -Rserver1,server2`

- `-r` = run on configured remote servers
- `-R` = run on specified remote servers

Start remote server:

`jmeter-server`

Stop remote servers after test:

`jmeter -n -t test-plan.jmx -X`

- `-X` = exit remote servers at end of test

## Common Examples

### Simple Run

`jmeter -n -t login-test.jmx -l login-results.jtl`

### Run and Generate Report

`jmeter -n -t login-test.jmx -l login-results.jtl -e -o login-report`

### Run with Parameters

`jmeter -n -t login-test.jmx -Jusers=200 -Jduration=300`

### Distributed Run

`jmeter -n -t login-test.jmx -R192.168.1.10,192.168.1.11 -l distributed-results.jtl`

## Quick Reference

| Option | Meaning                             |
|--------|-------------------------------------|
| `-n`   | Non-GUI mode                        |
| `-t`   | Test plan file                      |
| `-l`   | Results file                        |
| `-e`   | Generate HTML report                |
| `-o`   | Report output directory             |
| `-q`   | Additional properties file          |
| `-J`   | JMeter property                     |
| `-D`   | Java system property                |
| `-L`   | Log level                           |
| `-j`   | Log file                            |
| `-r`   | Run remote using configured servers |
| `-R`   | Run remote on specified servers     |
| `-X`   | Exit remote servers after test      |

## Platform Examples

### Windows

`jmeter.bat -n -t test-plan.jmx -l results.jtl -e -o report-folder`

### Linux/macOS

`./jmeter -n -t test-plan.jmx -l results.jtl -e -o report-folder`

## Tips

- Prefer **non-GUI mode** for load testing.
- Avoid heavy performance tests in the GUI.
- Clear the output folder before regenerating an HTML report.
- Use `-J` properties to make test plans reusable.
- Avoid committing large `.jtl` files to version control.