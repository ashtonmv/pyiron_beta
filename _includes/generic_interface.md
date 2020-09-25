{% highlight python %}
# Edit me!
from pyiron import Project  # Import Project object
pr = Project("demonstration")  # Create a project/folder
structure = pr.create_ase_bulk("Al")  # Create an aluminium bulk structure
for job_type in ["GpawJob", "Lammps", "Sphinx"]:   # Iterate over simulation codes
   job = pr.create_job(  # Create a job object
       job_type=job_type,
       job_name=job_type
   )
   job.structure = structure  # assign the structure
   job.run()  # Execute the calculation locally
table = pr.create_table()  # Create analysis object
table.add.get_energy_tot  # Define analysis functions
table.add.get_volume  # get the volume and total energy
{% endhighlight %}