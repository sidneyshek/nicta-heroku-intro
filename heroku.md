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
- Provides rollback, backups and build pipelines


### Supported stacks
- Ruby
- Node.Js
- Python
- Clojure
- Java - with embedded servlet container
- Scala - Play or custom app
- Grails (ugh)
- ...anything you want with a custom Procfile and/or build pack


### What is a Dyno?
- Small nodes - 512MB 1 CPU or 1GB 2 CPU
- 1 free small dyno per app. You get 'unlimited' apps for free
- 'Scale out' rather than 'scale up'


### Heroku databases
- Postgres with different grades
   - Free - 10k rows
   - Basic - 10M rows, $9/month
   - Prod instances from $50/month

- Can access via command line (psql) or SQL client


### Add-ons
- Managed services that can be easily added on (free and paid)
- [https://addons.heroku.com/](https://addons.heroku.com/)


	- Dynos are shutdown and moved around at will without your permission
		- Resilience
		- Statelessness

Database - Postgres. Free supports 10,000 rows. $9/mth for 10M

Add-ons - managed services that can be easily added on
e.g. memcache, SSL, other databases, monitoring, log capture
	- if there is an add on, typically you need to manage it through the Add-on interface rather than the provider's native website




## An example setup
1. Signup
2. [Install the Toolbelt](https://toolbelt.heroku.com)
3. Create an app
4. Deploy an app
5. Check out logs and database

- Create
- Create DB
- Install DB
- Build
- Check logs
- Access database
- Access shell
	- Procfile



## But my setup is different
- Procfile specifies how to start your app
- Custom build pack



## Traps to watch out for
- Heroku uptime - relies on AWS (East coast or EU)
- Dynos go up and down all the time
- Dynos shut down with no usage
- Load balancer has no server affinity
- Dynos are really small...so watch your JVM!
- App must start in < 60 seconds
- App must build in < 15 minutes
- App builds are in the 'cloud' with no access to your private network

- If your app doesn't start, check the number of dynos you have assigned

- pushing from subtrees
