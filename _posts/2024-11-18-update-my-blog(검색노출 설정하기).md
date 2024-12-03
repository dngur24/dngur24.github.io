Make My Blog(검색노출 설정하기)
==============================

1. google search console 검색, 해당 페이지 접속 
> 시작하기 버튼 클릭
> url 접두어을 선택
> https://자신의 깃허브 블로그 주소/ 를 입력
> '소유권 확인' 이라는 페이지가 뜨면 google~~~.html 파일을 다운받기
> 다운받은 html파일을 _config.yml이 있는 디렉터리로 이동(vscode를 이용한다면 commit까지 필수)
> 확인 버튼을 누르고 '소유권이 자동으로 확인됨' 문구가 나와야 한다

2. google search console에 sitemap.xml 제출-1
> _config.yml이 있는 디렉터리에 sitemap.xml파일을 생성
> sitemap.xml 파일에 밑에 있는 코드 삽입

```html
<note>
---
layout: null
---

<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd"
        xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
    {% for post in site.posts %}
    <url>
        <loc>{{ site.url }}{{ post.url }}</loc>
        {% if post.lastmod == null %}
        <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
        {% else %}
        <lastmod>{{ post.lastmod | date_to_xmlschema }}</lastmod>
        {% endif %}

        {% if post.sitemap.changefreq == null %}
        <changefreq>weekly</changefreq>
        {% else %}
        <changefreq>{{ post.sitemap.changefreq }}</changefreq>
        {% endif %}

        {% if post.sitemap.priority == null %}
        <priority>0.5</priority>
        {% else %}
        <priority>{{ post.sitemap.priority }}</priority>
        {% endif %}

    </url>
    {% endfor %}
</urlset>
</note>
```

> 당연히 파일도 commit을 한다

3. google search console에 sitemap.xml 제출-2
> google search console 페이지 왼쪽에 한자 석 삼 같이 생긴 기호 클릭, sitemap 항목 선택
> '새 사이트맵 추가' 부분에 sitemap.xml을 입력 
>>(https://깃허브 블로그 주소/sitemap.xml)의 형태가 되어야 함

>제출된 사이트맵 항목에서 상태를 확인한다.
>> 제출 후 곱바로 반영되지 않는 점을 유의하며 기다린다. 
