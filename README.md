# Et_todo_list

```
│  users         |                         |                       │
|----------------|-------------------------|-----------------------|
│id              │serial                   │primary key            │
│first_name      │varchar(255)             │not null default ''    │
│last_name       │varchar(255)             │not null default ''    │
│email           │varchar(255)             │not null unique        │
|hashed_password |char(60)                 │not null               │
│created_at      │timestamp with time zone │not null default now() │
│updated_at      │timestamp with time zone │not null default now() │


┌─────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                        users_tasks                                              │
├────────────────┬─────────────────────────┬──────────────────────────────────────────────────────┤
│id              │serial                   │primary key                                           │
│user_id         │integer                  │not null references users(id) on delete cascade index │
|task_id         │integer                  │not null references tasks(id) on delete cascade index │
│created_at      │timestamp with time zone │not null default now()                                │
│updated_at      │timestamp with time zone │not null default now()                                │
└────────────────┴─────────────────────────┴──────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                                          Tasks                                           │
├─────────────┬─────────────────────────┬──────────────────────────────────────────────────┤
│id           │serial                   │primary key                                       │
│title        │varchar(255)             │not null default ''                               │
│description  │text                     │not null default ''                               │
│created_at   │timestamp with time zone │not null default now()                            │
│updated_at   │timestamp with time zone │not null default now()                            │
└─────────────┴─────────────────────────┴──────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                                         Lists                                            │
├─────────────┬─────────────────────────┬──────────────────────────────────────────────────┤
│id           │serial                   │primary key                                       │
│title        │varchar(255)             │not null default ''                               │
│date         │varchar(255)             │not null default ''                               │
│description  |text                     |not null default ''                               |
│user_id      |integer                  │not null references users(id) on delete cascade index                                
│created_at   │timestamp with time zone │not null default now()                            │
│updated_at   │timestamp with time zone │not null default now()                            │
└─────────────┴─────────────────────────┴──────────────────────────────────────────────────┘
```
