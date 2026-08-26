# Database Schema

### Users
* **`id`** (PK)
* `email`
* `password_hash`
* `created_at`

### Invitations
* **`id`** (PK)
* `user_id` (FK -> `Users.id`)
* `content`
* `status`
* `created_at`
* `completed_at`

### Reflections
* **`id`** (PK)
* `invitation_id` (FK -> `Invitations.id`)
* `content`
* `status`
* `released_at`

### Deliveries (Matching)
* **`id`** (PK)
* `reflection_id` (FK -> `Reflections.id`)
* `recipient_user_id` (FK -> `Users.id`)
* `delivered_at`
* `read_at`

### Stars (Constellation)
* **`id`** (PK)
* `user_id` (FK -> `Users.id`)
* `delivery_id` (FK -> `Deliveries.id`)
* `brightness_level`
* `created_at`