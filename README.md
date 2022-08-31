ADDED FOR BOTH GATEAPI and GATEWAY:
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
    - At first i tought this was a problem with the environment configand services, since
      the problem was found on all endpoints, but it seemed to be a code issue.
    - Code problems on many endpoints:
        Performance degraded due to local storage of values and looping over this.
        When more records where added to the databases, more local memory was used, 
        and there was a bigger loop


Question 2: How do you fix it ?
    - removing caching results, getting only the ones needed, or for example for validation,
      searching for the product-id in the database instead of storing all records in local memory
      and searching over this.
      for the LIST ORDERS endpoint, this was solved adding (a very primitive) pagination.


(bonus): Fix it --- > FIXED FOR FASTAPI, RUN PERFORMANCE TESTS OVER FASTAPI ENDPOINTS.