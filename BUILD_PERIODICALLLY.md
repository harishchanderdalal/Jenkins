# Jenkins will accept 5 parameter lets discuss one by one
    
    * * * * * 

1. First parameter- specify minute and range will vary from 0-59

2. Second parameter- specify hours and range will vary from 0-11

3. Third parameter- specify day and range will vary from 0-7 here 0 and 7 will be Sunday

4. Fourth parameter- specify month and range will vary from 1-12

5. Fifth parameter- specify year so here you can specify *

# Examples

1. If you specify    00 22 * * *  it means your build will run daily @ 10 PM

2. If you specify    50 * * * *  it means your build will run daily  50 min  after every hour

3. If you specify    00 22 1 * *  it means your build will run every Monday @ 10 PM

<pre><code>
 ┌───────────── minute (0 - 59)
 │ ┌───────────── hour (0 - 23)
 │ │ ┌───────────── day of month (1 - 31)
 │ │ │ ┌───────────── month (1 - 12)
 │ │ │ │ ┌───────────── day of week (0 - 6) (Sunday to Saturday;
 │ │ │ │ │                                       7 is also Sunday on some systems)
 │ │ │ │ │
 │ │ │ │ │
 * * * * *  command to execute </pre></code
 
 # NOTE - H
 If you use H insted of * then jenkins will check free slot when to run, It's good to remove parallel. Jenkins will remove load distribution the load of job  
