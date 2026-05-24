GitHub actions have a few vocabulary words that are useful to know:

- workflow -- a YAML file that defines everything else -- the event, the job(s), the step(s), etc.  A repo on GitHub can have any number of workflows, meaning any number of YAML files that define what you want to do. Each of these is run in parallel, on a separate VM.

- event -- what triggers the workflow running? Normally, it'll be a "git push". It could also be a pull request. When this event happens, then the workflow starts to run.

- job -- this is what should happen when the workflow starts to run. You can have any number of jobs inside of a workflow YAML file. Normally, all of the jobs inside of a workflow run in parallel.

- step -- this is the actual command that runs inside of a job. Each job can contain any number of steps. These are typically going to be things like "uv run XYZ".

- runner -- the VM on which it actually executes.

The core idea is that you're going to run tests of some sort on your code. If something fails, then you'll get e-mail telling you what failed. You can also check on the Web site.

If everything works, then it succeeds silently.


The workflow files go inside of a .github directory inside of your repo's top level. Under that, you'll have a "workflow" directory. The YAML files go inside of that directory.
