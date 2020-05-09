
If there is a change in the URL of a WordPress website, all the occurrences of the old URL needs to be replaced by the new URL in the website database. Following are the list of MySQL queries to do this.

```
UPDATE `wp_posts` SET post_content = REPLACE(post_content, 'src="http://old url', 'src="http://new url')
WHERE post_content LIKE '%src="http://old url%';
```

```
UPDATE wp_posts SET post_content = REPLACE(post_content, "src='http://old url", "src='http://new url")
WHERE post_content LIKE "%src='http://old url%";
```

```
UPDATE wp_posts SET post_content = REPLACE(post_content, 'href="http://old url', 'href="http://new url')
WHERE post_content LIKE '%href="http://old url%';
```

```
UPDATE wp_posts SET post_content = REPLACE(post_content, "href='http://old url", "href='http://new url")
WHERE post_content LIKE "%href='http://old url%";
```

```
UPDATE wp_posts SET pinged = REPLACE(pinged, 'http://old url', 'http://new url')
WHERE pinged LIKE '%http://old url%';
```

```
UPDATE wp_comments SET comment_author_url = REPLACE(comment_author_url, 'http://old url', 'http://new url')
WHERE comment_author_url LIKE '%http://old url%';
```

```
UPDATE wp_comments SET comment_content = REPLACE(comment_content, 'http://old url', 'http://new url')
WHERE comment_content LIKE '%http://old url%';
```

```
UPDATE wp_postmeta SET meta_value = REPLACE(meta_value, 'http://old url', 'http://new url')
WHERE meta_value LIKE '%http://old url%';
```

```
UPDATE wp_options SET option_value = "http://new url" WHERE wp_options.option_name = 'siteurl';
```

```
UPDATE wp_options SET option_value = "http://new url" WHERE wp_options.option_name = 'home';
```

These queries are very nicely explained in the below link: <br />
https://isabelcastillo.com/mysql-wordpress-http-to-https
