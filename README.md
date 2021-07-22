Subprocess is used to execute the linux system commands using python.
Three test methods to check whether phyiscal volume, Volume group and Logical Volume is created or not using the unittest framework

In cli.py, the cli to run the tests is created using the argument parser.

In the test_pvcreate method, the physical volume is created using the pvcreate command and the disk name which is retrieved from the cli. Then using the pvdisplay command, asserted whether the physcial volume is created or not
In the tearDown method, pv is destroyed

In the test_vgcreate method, physical volume and the volume group is created and then checked whether the volume group is created using the vgdisplay command
In the tearDown method, pv and vg is destroyed

In the test_xlvcreate method, physical volume, volume group and logical volume is created and then checked whether the logical volume is created using the lvdisplay command
In the tearDown method, pv, vg and lv is destroyed

Commands used for executing the code:
For creating pv : sudo python3 cli.py --test pvcreate --disk /dev/sdb

For creating vg : sudo python3 cli.py --test vgcreate --disk /dev/sdb --vgname vg1

For creating lv : sudo python3 cli.py --test lvcreate --disk /dev/sdb --vgname vg1 --lvname lv1 --size 1000M
