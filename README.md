
- Delete product rpc call
    - Wire into smoketest.sh
    - Wire into perf-test
    - Wire unit-test for this method
- Enhance order service
    - List orders rpc call
    - Wire into smoketest.sh
    - Wire into perf-test
    - Wire unit-test for this method

Execute performance test
Question 1: Why is performance degrading as the test run longer ?
- Performance seem to degrade as postgresdb get more populated, same tests running deletions after every create show improved results.
Question 2: How do you fix it ?
- giveing more resources to db's.
(bonus): Fix it