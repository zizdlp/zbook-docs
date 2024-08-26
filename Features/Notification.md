# Notifications

ZBook uses `websockets` to push notifications to users, covering various aspects such as `system`, `repository`, `followers`, and `comments`. System notifications are primarily sent by the system or administrators. For repositories, if another user (User A) follows a user (User B), User A will receive a notification if User B creates a visible repository. Similarly, `follower notifications` inform User B when someone (User A) follows them. Comment notifications alert User A when another user (User B) comments on User A's repository or comments under User A's posts.

![Notifications](./assets/通知.png)

## System Notifications

Currently, when a new user registers, they receive a welcome system notification containing a link with usage instructions. Additionally, administrators can send system notifications. Specifically, administrators can click to create a new system notification in their user sidebar, fill in the details in the popup, and confirm.

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Title     | Notification title                        |
| Username  | The user to be notified                   |
| Link      | Optional; if provided, the user will be redirected upon clicking |
| Content   | The content of the notification           |

![System Notifications](./assets/通知.gif)