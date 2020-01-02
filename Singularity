
Bootstrap: docker
From: nugent68:ansys-nersc
#From: nvidia/cuda:10.2-runtime-centos7 #tmp test only
 

%post
	[[ -d /opt ]] || mkdir /opt
	#cd /opt
	#wget --quiet https://www.ansys.com/download/software/ansys.tgz
	# OR, if just want to use the tgz that was already created, assuming no private content
	#wget --quiet https://download.dropbox/USERNAME/.../ansys.tgz

	#tar xfz ansys.tgz

	# hacks that maybe useful during development/troubleshooting 
	# outside the cluster where scratch is not available and still want to write files to it temporarily
  # 41274 is uid for hjohansen
	mkdir -p       /global/scratch/penugent
	chown -R 12645 /global/scratch/penugent
	mkdir -p       /global/scratch/hjohansen
	chown    41273 /global/scratch/hjohansen
	chown -R 12645:504 /opt

	
%runscript
	#TZ=PST8PDT /opt/ansys/bin/ansys $@
	TZ=PST8PDT /bin/bash

%help
	Please see https://github.com/tin6150/ansys 
    
# Pull container from singularity-hub: 
# singularity pull --name ansys.sif shub://tin6150/ansys
# run binary specified by container in %runscript
# ./ansys.sif


# manual build cmd if not using singularity-hub:
# sudo singularity build  ansys.sif Singularity 2>&1  | tee singularity_build.log
#
# singularity 2.6 cmd:
# sudo singularity build --writable ansys.sif Singularity 2>&1  | tee singularity_build.log
# troubleshooting container by shelling into it:
# sudo singularity exec -w ansys.sif /bin/bash

# Dirac has Singularity 3.2



