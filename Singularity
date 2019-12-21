
Bootstrap: docker
#From: 68nugent:ansys-nersc:latest 
From: nvidia/cuda:10.2-runtime-centos7
 

%post
	#wget --quiet https://www.ansys.com/download/software/ansys.tgz
	# OR, if just want to use the tgz that was already created, assuming no private content
	#wget --quiet https://download.dropbox/USERNAME/.../ansys.tgz

	cd /opt
	#tar xfz ansys.tgz

	# hacks that maybe useful during development/troubleshooting 
	# outside the cluster where scratch is not available and still want to write files to it temporarily
	mkdir -p       /global/scratch/hjohansen
	chown    41273 /global/scratch/hjohansen
	chown -R 41273 /opt
	
%runscript
	TZ=PST8PDT /opt/ansys/bin/ansys $@

%help
	Please see https://github.com/tin6150/ansys 
    
# Pull container from singularity-hub: 
# singularity pull --name ansys.img shub://tin6150/ansys
# run binary specified by container in %runscript
# ./ansys.img


# manual build cmd if not using singularity-hub:
# sudo singularity build --writable ansys.img Singularity 2>&1  | tee singularity_build.log
# troubleshooting container by shelling into it:
# sudo singularity exec -w ansys.img /bin/bash

# Dirac has Singularity 3.2



