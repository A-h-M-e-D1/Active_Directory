# Main Concepts Before Getting Deep into Active Directory and Windows Server

## 1. What is Virtualization?
Virtualization is a technology that allows you to run multiple operating systems on a single physical host using a **hypervisor**.

### Types of Hypervisors:
- **Type 1 (Bare Metal):**  
  Runs directly on the hardware.  
  Examples: `VMware ESXi`, `Microsoft Hyper-V (Server Edition)`.

- **Type 2 (Hosted):**  
  Runs inside an existing operating system.  
  Examples: `VMware Workstation`, `Oracle VirtualBox`.

---

## 2. Requirements to Create Virtual Machines:
To create virtual machines, you need:
1. **Memory (RAM)**  
2. **Storage (Disk space)**  
3. **CPU (Processor)**  
4. **Network Interface**

---

## 3. Why Do We Need Active Directory?

### ليه احتاجنا Active Directory؟
ببساطة، نظام ويندوز بيشتغل بشكل افتراضي باستخدام **Workgroup**، وده كويس في بيئات صغيرة.

لكن مثلًا لو عندي شركة فيها 5 أجهزة أو أكتر وعاوز أنشئ لكل واحد يوزر وباسورد، مش منطقي أروح على كل جهاز وأعمل الأكونت يدوي.  
تخيل لو فيه 100 جهاز! هياخد وقت ومجهود كبير جدًا.

علشان كده بدأنا نستخدم **Active Directory**، واللي بيخليني أقدر أعمل كل الإعدادات (Configuration) من مكان مركزي، وهو السيرفر اللي فيه الدومين.

---

## 4. Configuration Services in Active Directory
Active Directory allows you to configure and manage various services across your network:
- **DHCP** (Dynamic Host Configuration Protocol)
- **DNS** (Domain Name System)
- **Group Policy** (to enforce rules and restrictions)
- **Disaster Recovery** (DR)
- **Print Server**
- **WDS** (Windows Deployment Services)
