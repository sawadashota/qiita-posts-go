# Qiita Team Posts Go
## インストール
```bash
$ go get git@github.com:sawadashota/qiita-posts-go.git
```

## やること
Qiita::Teamの投稿を構造体で返します。

```go
type Post struct {
	Body         string      `json:"body"`
	Coediting    bool        `json:"coediting"`
	CreatedAt    string      `json:"created_at"`
	ID           string      `json:"id"`
	Private      bool        `json:"private"`
	RenderedBody string      `json:"rendered_body"`
	Title        string      `json:"title"`
	UpdatedAt    string      `json:"updated_at"`
	URL          string      `json:"url"`
	User         User        `json:"user"`
}

type User struct {
	Description       interface{} `json:"description"`
	FacebookID        interface{} `json:"facebook_id"`
	FolloweesCount    int         `json:"followees_count"`
	FollowersCount    int         `json:"followers_count"`
	GithubLoginName   interface{} `json:"github_login_name"`
	ID                string      `json:"id"`
	ItemsCount        int         `json:"items_count"`
	LinkedinID        interface{} `json:"linkedin_id"`
	Location          interface{} `json:"location"`
	Name              string      `json:"name"`
	Organization      interface{} `json:"organization"`
	PermanentID       int         `json:"permanent_id"`
	ProfileImageURL   string      `json:"profile_image_url"`
	TwitterScreenName interface{} `json:"twitter_screen_name"`
	WebsiteURL        interface{} `json:"website_url"`
}
```

## 使い方
### 投稿の取得
```
Posts(page int, teamName string, token string).Get()
```

ステータスコードと投稿のスライス`[]Post`を返します。