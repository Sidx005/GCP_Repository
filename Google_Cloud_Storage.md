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

