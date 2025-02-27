-- Таблица пользователей
```
Table users {
  id integer [primary key]
  username varchar
  created_at timestamp
}
```

-- Таблица постов
```
Table posts {
  id integer [primary key]
  user_id integer
  text text
  place_id integer
  created_at timestamp
}
```

-- Таблица комментариев
```
Table comments {
  id integer [primary key]
  post_id integer
  user_id integer
  text text
  created_at timestamp
}
```
-- Таблица лайков
```
Table likes {
  id integer [primary key]
  post_id integer
  user_id integer
  created_at timestamp
}
```
-- Таблица подписок
```
Table subscriptions {
  id integer [primary key]
  follower_id integer
  followed_id integer
  created_at timestamp
}
```
-- Таблица мест
```
Table places {
  id integer [primary key]
  name varchar
  created_at timestamp
  coordinates varchar
  address varchar
}
```
-- Таблица фотографий
```
Table photos {
  id integer [primary key]
  place_id integer
  post_id integer
  url varchar
  created_at timestamp
  }
```
-- Связи
```
Ref: posts.user_id > users.id
Ref: comments.post_id > posts.id
Ref: comments.user_id > users.id
Ref: likes.post_id > posts.id
Ref: likes.user_id > users.id
Ref: subscriptions.follower_id > users.id
Ref: subscriptions.followed_id > users.id
Ref: posts.place_id > places.id
Ref: photos.post_id > posts.id
Ref: photos.place_id > places.id
```
