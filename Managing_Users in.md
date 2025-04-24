## AD DS Initial Administrative Tasks Summary

### 1. Review Existing OUs and Users

As the new domain administrator, your first task is to check the existing **Organizational Units (OUs)** and user accounts in **Active Directory (AD)**, ensuring they align with the updated organisational structure.

---

### 2. Deleting Extra OUs and Users

If there's an extra OU that no longer exists in the organisational chart (e.g., a closed department), it should be deleted.

#### ⚠️ Issue:
When you attempt to delete an OU, you may receive an error because **OUs are protected against accidental deletion** by default.

#### ✅ Solution:
1. In AD Users and Computers, go to `View > Advanced Features`.
2. Right-click the OU > `Properties` > `Object` tab.
3. Uncheck **"Protect object from accidental deletion"**.
4. Now, you can safely delete the OU.

> Note: Deleting an OU will also delete any users or groups under it.

Then, verify the remaining users and departments. **Add or remove users** as needed to match the organisational chart.

---

### 3. Delegation

**Delegation** is the process of assigning specific administrative privileges over OUs to certain users—without making them full domain administrators.

#### 📌 Use Case:
Give **Phillip** (IT support) the ability to reset passwords in the **Sales**, **Marketing**, and **Management** OUs.

#### 🛠️ Steps to Delegate Control:
1. Right-click the **Sales OU** > Select **"Delegate Control"**.
2. Add the user (use "Check Names" to verify).
3. Select **"Reset user passwords and force password change at next logon"**.
4. Click **Next** > **Finish**.



