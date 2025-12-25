# Install apptainer following this guide.

https://apptainer.org/docs/admin/main/installation.html

# Build the image

sudo apptainer build google_antigravity.sif ./google_antigravity.def

# Launching antigravity in apptainer, this will isolate the home folder. 
# If you wanted a path mounted for a project you are working on you can add --bind /<path>/<toproject>
mkdir -p /tmp/apptainer/home

apptainer shell --no-mount ~ --bind /tmp/apptainer/home/:/home/$USER --bind /run ./google_antigravity.sif 

antigravity
