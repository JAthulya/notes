do this

sudo fdisk -l -> display patitions exists/ see disk partition table
sudo dd if=[location of the USB drive] of=[the destination of outputfile with extension of .img]
ex- dd if=/dev/sdb of=/home/homer/Desktop/test.img

**Software based writeblocker**
windows+r "regedit"
1.  Go to the HKEY_LOCAL_MACHINE \ SYSTEM \ CurrentControlSet \ Control
2. If there is no key called “StorageDevicePolicies”, create it. You do this by right-clicking the HKEY_LOCAL_MACHINE \ SYSTEM \ CurrentControlSet \ Control, and selecting New > Key from the menu
3. 1.  Name the new Key “StorageDevicePolicies” and press “Enter”

4.  Select the StorageDevicePolicies key, right click on the key and choose new -> DWORD(32-bit) Value (as shown below)
5. Name the new value “WriteProtect”
6.  Right click the WriteProtect value and Choose Modify
7.  In the Value data: box enter 1
8. Exit the registry editor and restart your computer (save your work before restart the computer!).
9.  To reverse, just delete the new WriteProtect value (or set the value to 0) and restart your computer.
10.  Test your software based write blocker.
11.  **_After testing, please remove the StorageDevicePolices key!_**

1.      Use the **Windows key + R** keyboard shortcut to open the **Run** command.

2.      Type **gpedit.msc** and click **OK** to open the Local Group Policy Editor.

3.      Browse the following path:

Computer Configuration > Administrative Templates > System > Removable Storage Access

4.      On the right side, double-click the **Removable Disks: Deny write access** policy.
5.      On the top-left, select the **Enabled** option to activate the policy.

6.      Click **Apply**.

7.      Click **OK**.
