# Installation of torrent package

*npm install -g torrent*
*torrent --version*

# Q1 - Create a torrent containing this image

*torrent create IPFS-command.png -o outfile.torrent*

# Q2 - Now copy the image to a new directory named partition1 and create a torrent of this folder

I copied the image into the partition1 directory manually.

*torrent create partition1 -o outfile2.torrent*

# Q3 - Copy the partition1 folder and then generate the associated torrent

I copied the folder manually and renamed it partition2.

*torrent create partition2 -o outfile3.torrent*

# Install the IPFS Desktop App

I basically followed the steps to download and install the app manually.

# Install the IPFS Desktop CLI

I downloaded the zip file and extracted it.

*cd Decentralized\kubo_v0.26.0_windows-amd64\kubo*
*.\ipfs.exe --version*
*$GO_IPFS_LOCATION = pwd*
*if (!(Test-Path -Path $PROFILE)) { New-Item -ItemType File -Path $PROFILE -Force }*
*notepad $PROFILE*
*Add-Content $PROFILE "`n[System.Environment]::SetEnvironmentVariable('PATH',`$Env:PATH+';;$GO_IPFS_LOCATION')"*
*Set-ExecutionPolicy RemoteSigned*
*& $profile*
*cd ~*
*ipfs --version*

# Q1 - Upload the previous image to IPFS

*ipfs add IPFS-command.png*

# Q2 - Now upload partition1 to IPFS

*ipfs add -r partition1*

# Q3 - Copy the partition1 folder and then generate the associated torrent

*torrent create partition2 -o outfile3.torrent*
