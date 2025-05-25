## High-Level Service Breakdown

| **Service**               | **Responsibility**                                                                                                                                         |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **API Gateway**           | Single entry point for all external clients. Handles routing, rate-limiting, TLS termination, auth plug-ins.                                               |
| **Auth & Security Service** | OAuth2/JWT issuance & validation, user/password login, Google social login, optional MFA, scopes & roles.                                                |
| **User Profile Service**  | CRUD for user profiles, preferences (including calendar opt-in), MFA settings, avatar management.                                                          |
| **Social Feed Service**   | Posts, comments, reactions, “mentions” tab logic, feed curation.                                                         |
| **Media Service**         | Photo/video upload, thumbnail/transcode pipeline, encrypted storage, ACL enforcement.                                                            |
| **Event Service**         | Master event calendar CRUD, Google Calendar sync (via OAuth scopes), personal-calendar export.                                                             |
| **Notification Service**  | Email dispatch (Gmail SMTP/API) for invites, reminders; push eventually via FCM/APNs.                                                                      |
| **Group/Permissions Service** | Optional: defines “Family” or custom groups, ACLs for sharing posts/albums.                                                                            |
| **Gateway Config & Discovery** | (e.g. Consul / Kubernetes DNS) for service discovery, health checks.                                                                                  |
| **Message Broker**        | async workflows: media transcode, email jobs, feed updates.                                                            |
