{% highlight python %}
# Edit me!
table.add["job_type"] = get_code_type  # Add custom analysis function
table.run()  # Execute the analysis
print(table.get_dataframe())  # Results are summarized in DataFrame
job = pr.create_job(  # Create a job object
   job_type=pr.job_type.Sphinx,  # Use project to select job type
   job_name="spx_hpc"  # Set job name
)
job.structure = structure  # Assign atomistic structure
print(job.server.list_queues())  # List of available queues
# job.server.queue = "cm"  # Select a queue
job.server.cores = 4  # Set number of cores
job.server.run_time = 1000  # Set run time
job.run()  # The job is executed on the HPC cluster
{% endhighlight %}