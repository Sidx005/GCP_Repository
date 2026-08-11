## Upload Object in Bucket

<img width="705" height="513" alt="image" src="https://github.com/user-attachments/assets/b5e66b5f-f383-4097-8acc-d18585824065" />


<img width="957" height="414" alt="image" src="https://github.com/user-attachments/assets/5a36ff25-09c7-43c3-b9bf-301fbd0e0740" />


<img width="689" height="377" alt="Screenshot 2026-08-11 at 11 43 30 AM" src="https://github.com/user-attachments/assets/611074ec-8796-40ba-83f6-f2278617c977" />



<img width="645" height="434" alt="Screenshot 2026-08-11 at 11 41 55 AM" src="https://github.com/user-attachments/assets/afb36d0f-1efd-4207-b824-049e23b25310" />



<img width="612" height="334" alt="image" src="https://github.com/user-attachments/assets/26bd5bb8-b112-49b4-9b12-bf8e0af7a47d" />


<img width="667" height="362" alt="image" src="https://github.com/user-attachments/assets/a634f899-421f-4a1b-acca-815b1fde6b49" />




## Object Lifecycle

* **Object Lifecycle** = rules that automatically manage objects in a GCS bucket.
* Used mainly for **cost optimization and automatic cleanup**.
* Lifecycle rule = **Condition → Action**.

**Common actions:**

* **Delete** → Remove object
* **SetStorageClass** → Change storage class
* **Abort incomplete uploads** → Remove unfinished uploads

**Common conditions:**

* Object age
* Creation date
* Storage class
* Object name prefix/suffix
* Number of newer versions

**Example:**

```text
Age > 30 days  → Nearline
Age > 90 days  → Coldline
Age > 365 days → Delete
```

**Key point:** Lifecycle rules are evaluated **asynchronously**, so actions may not happen exactly when the condition is reached.


<img width="625" height="276" alt="image" src="https://github.com/user-attachments/assets/d4b285dc-7aaf-4e94-95a7-73f8d516b51e" />


<img width="487" height="324" alt="image" src="https://github.com/user-attachments/assets/89a2eda3-e8e2-4919-8c15-fd825ad39265" />


<img width="457" height="379" alt="image" src="https://github.com/user-attachments/assets/3c550f4a-207d-42dc-ab4f-814deb843752" />


<img width="547" height="368" alt="image" src="https://github.com/user-attachments/assets/f41a55a2-2300-42a5-82c0-b41bb781ff63" />


<img width="536" height="532" alt="image" src="https://github.com/user-attachments/assets/f84a158f-a9df-481f-aa9a-40f5faf19c8c" />



## Access Control

## GCS Access Control — Short Notes

### 1. Two Access Control Types

| Type             | Meaning                                         |
| ---------------- | ----------------------------------------------- |
| **Uniform**      | Same access policy for all objects in a bucket  |
| **Fine-grained** | Access can be configured for individual objects |

### 2. Fine-Grained Access

* Uses **object-level ACLs**.
* Each object can have different permissions.
* Example:

  ```text
  file1.jpg → Public
  file2.jpg → Private
  file3.jpg → User A (Reader)
  ```
* Useful when different objects need different access.

### 3. Uniform Access

* Access is managed at the **bucket level**.
* Object-level ACLs are disabled.
* All objects follow the bucket's IAM permissions.
* Recommended by Google as a **best practice** because it is simpler to manage.

### 4. Common Permissions

* **Reader** → Can read/access the object.
* **Owner** → Full control over the object.
* **All users (`allUsers`)** → Anyone on the internet.
* **All authenticated users (`allAuthenticatedUsers`)** → Any authenticated Google account.

### Key Difference

```text
Fine-grained → Object-level access
Uniform      → Bucket-level IAM access
```

**Remember:** When switching to **Uniform**, existing object ACLs are removed/ignored, so individual object permissions can no longer be managed through ACLs.


<img width="527" height="375" alt="image" src="https://github.com/user-attachments/assets/629c40fe-28fe-4bb8-9eef-55f8c812ad0d" />


Remove all users reading permission i.e dont make it public

<img width="646" height="442" alt="image" src="https://github.com/user-attachments/assets/74d0a17f-67ba-430a-91c2-808d744f7536" />

