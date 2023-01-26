## 1. auth(인증관련)

### 1-1. login(로그인)

- method: POST
- url: localhost:3000/api/login
- bodyParams: email, password

### 1-2. logout(로그아웃)

- method: POST
- url: localhost:3000/api/logout
- header: X-Auth-Token

### 1-3. register(가입)

- method: POST
- url: localhost:3000/api/user
- bodyParams: email, password

### 1-4. user

- method: GET
- localhost:3000/api/user
- header: X-Auth-Token
- response:

```
{
  _id: "###",
  email: "###"
}
```

## 2. article(게시글)

### 2-1. article 게시글 작성

- method: POST
- url: localhost:3000/api/article
- auth: true
- header: X-Auth-Token
- bodyParams: content
- response:

```
{
  userId: "###",
  userName: "###",
  content: "###",
  createdAt: "###",
  commentCount: "###",
  likeCount: "###",
  likeUsers: ["###"],
}
```

### 2-2. article 게시글 수정

- method: PUT
- url: localhost:3000/api/article
- auth: true
- header: X-Auth-Token
- bodyParams: content, \_id
- response:

```
{
  userId: "###",
  userName: "###",
  content: "###",
  createdAt: "###",
  commentCount: "###",
  likeCount: "###",
  likeUsers: ["###"],
}
```

### 2-3. article 게시글 삭제

- method: DELETE
- url: localhost:3000/api/article
- auth: true
- header: X-Auth-Token
- bodyParams: \_id

### 2-4. articles 게시글 목록

- method: GET
- url: localhost:3000/api/articles/:currentPage
- auth: 선택
- header: X-Auth-Token(선택)
- urlParams: currentPage
- response:

```
{
  articleList: [
    {
      userId: "###",
      userName: "###",
      content: "###",
      createdAt: "###",
      commentCount: "###",
      likeCount: "###",
      likeUsers: ["###"],
    },
    ...
  ],
  totalPage: ###,
  menuPopup:'###',
  editMode:'###'
}
```

### 2-5. article 게시글 한개

- method: GET
- url: localhost:3000/api/articles/:\_id
- auth: false
- urlParams: \_id
- response:

```
{
  userId: "###",
  userName: "###",
  content: "###",
  createdAt: "###",
  commentCount: "###",
  likeCount: "###",
  likeUsers: ["###"],
}
```

## 3. like

### 3-1. like 표시

- method: PUT
- url: localhost:3000/api/like
- auth: true
- header: X-Auth-Token
- bodyParams: articleId

### 3-2. like 해제

- method: PUT
- url: localhost:3000/api/cancellike
- auth: true
- header: X-Auth-Token
- bodyParams: articleId

### 3-3. likes

- method: GET
- url: localhost:3000/api/likes/:currentPage
- auth: true
- header: X-Auth-Token
- urlParam: currentPage
- response:

```
{
    articleList: [
      {
        userId: "###",
        userName: "###",
        content: "###",
        createdAt: "###",
        commentCount: "###",
        likeCount: "###",
        likeUsers: ["###"],
      },
      ...
    ],
    totalPage: ###,
    menuPopup:'###',
    editMode:'###'
}
```

## 4. comment

### 4-1. comment 추가

- method: POST
- url: localhost:3000/api/comments
- auth: true
- header: X-Auth-Token
- bodyParams: articleId, content
- response:

```
{
  userId: "###",
  userName: "###",
  articleId: "###",
  content: "###",
  createdAt: "###",
}
```

### 4-2. comment 삭제

- method: DELETE
- url: localhost:3000/api/comments
- auth: true
- header: X-Auth-Token
- bodyParams: \_id, articleId

### 4-3 comment 목록

- method: GET
- url: localhost:3000/api/comments/:\_id
- response:

```
[
  {
    userId: "###",
    userName: "###",
    articleId: "###",
    content: "###",
    createdAt: "###",
  },

]

```
