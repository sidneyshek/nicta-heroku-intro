## Getting Started with Heroku



## What is Heroku?
- Platform-as-a-Service providing
   - Some CPUs ('dynos')
   - Optional database (Postgres)
   - Optional add-ons
   - Load balancer in front
- Runs on AWS (US East or Europe)


### Why?
- Write code, don't manage infrastructure
- Provides app management features like:
   - Rollback
   - Backups
   - Build pipelines


### Supported stacks
- Ruby
- Node.js
- Python
- Clojure
- Java - with embedded servlet container
- Scala - Play or custom app
- Grails (ugh)
- ...anything you want with custom Procfile and/or build pack


### What is a Dyno?
- 512MB 1 CPU or 1GB 2 CPU
- 1 free small dyno per app
- 'Unlimited' apps for free
- 'Scale out' rather than 'scale up'


### Heroku databases
- Postgres with different grades
   - Free - 10k rows
   - Basic - 10M rows, $9/month
   - Prod instances from $50/month

- Can access via command line (psql) or SQL client


### Add-ons
- Managed services that can be easily added on
- [https://addons.heroku.com/](https://addons.heroku.com/)



## An example setup
1. Signup
2. [Install the Toolbelt](https://toolbelt.heroku.com)
3. Create an app
4. Deploy an app
5. Check out logs and database



## Traps to watch out for


### Dynos change a lot
Dynos go up and down all the time

Dynos shut down if no activity

Load balancer has no server affinity

Dynos are really small...so watch your JVM!

Remember: Heroku relies on AWS (East coast or EU)

**_Small, stateless and resilient components!_**

**_Try something like [Pingdom](https://www.pingdom.com) for pinging/monitoring_**


## Building and starting apps
- Apps must start in < 60 seconds
- Apps must build in < 15 minutes
- Apps built in the 'cloud'
   - Include private libraries in your repo
- Easiest to push entire repos instead of subtrees
- If your app doesn't start, check the number of dynos you have assigned

