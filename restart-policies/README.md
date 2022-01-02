Self-Healing with Restart Policies: 

Build self-healing pods with restart policies. Kubernetes can automatically restart containers when they fail, and we've already talked about using probes to detect container failures. Restart Policies basically control what happens once we detect that a container is unhealthy, so you're able to define when your containers are automatically restarted or even say that you don't want your containers to be automatically restarted.

There are 3 different kinds of Restart Policies:

Always - This is the default restart policy. So if you don't define one, this is the one that's going to take effect. With this policy, containers will always be restarted if they stop or become unhealthy.

On Failure - On Failure will restart the container process only if the container process becomes unhealthy or exits with an error code. So if you have some software that is designed to run once to a successful completion and then stop, and it doesn't need to be run again, you want to use the On Failure policy. That's going to automatically restart the application if it fails, but if it succeeds and finishes, it won't be restarted.

Never - Never is essentially the opposite of the Always restart policy. No matter what happens, if a container completes successfully, or if it completes unsuccessfully, it will never be restarted.
You should use this restart policy for applications that should only run once and never be automatically restarted. 