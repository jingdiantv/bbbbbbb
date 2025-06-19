[
  {
    "bookSourceComment": "//by:cwjdb",
    "bookSourceGroup": "5.5",
    "bookSourceName": "VIP中文",
    "bookSourceType": 0,
    "bookSourceUrl": "http://m.xvipxs.net",
    "bookUrlPattern": "",
    "customOrder": 4,
    "enabled": true,
    "enabledCookieJar": false,
    "enabledExplore": true,
    "exploreUrl": "@js:\n    java.toast(\"正在努力加载中，请稍后\");\nvar sort = [];\nvar push = (title, url, type1, type2) => {\n    sort.push({\n        title: title,\n        url: url,\n        style: {\n            layout_flexGrow: type1,\n            layout_flexBasisPercent: type2\n        }\n    });\n};\nvar sites = [{\n        u: \"http://m.xvipxs.net/sort.html\",\n        ti: \"༺ˇ»`全部分类´«ˇ༻\"\n    },\n    {\n        u: \"http://m.xvipxs.net/top.html\",\n        ti: \"༺ˇ»`全部排行´«ˇ༻\"\n    }];\nfor (var site of sites) {\n    var o = org.jsoup.Jsoup.parse(java.ajax(site.u));\n    var s = o.select('.content li a');\n    push(site.ti, \"\", \"1\", \"1\");\n    for (var i = 0; i < s.size(); i++) {\n        var urls = String(s[i].attr(\"href\")).replace(/\\/(.*)-(.*)-(\\d+)\\//, \"/$1-$2-{{page}}/\");\n        if (s.length % 3 === 1) {\n            push(s[i].text(), urls, \"-1\", \"0.29\")\n        } else {\n            push(s[i].text(), urls, \"1\", \"0.25\")\n        }\n    }\n}\npush(\"༺ˇ»`全本小说´«ˇ༻\", `/full-{{page}}/`, \"1\", \"1\")\nJSON.stringify(sort);",
    "header": "{\"User-Agent\":\"Mozilla/5.0 (Linux; U; Android 13; zh-Hans-CN; PFJM10 Build/TP1A.220905.001) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/100.0.4896.58 Quark/6.13.6.581 Mobile Safari/537.36\",\"Accept-Language\":\"zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7\"}",
    "lastUpdateTime": 1746428505335,
    "respondTime": 180000,
    "ruleBookInfo": {
      "author": "a",
      "coverUrl": "c",
      "init": "@js:\nX = (x) => java.getString(x);\n({\n    n: X(\"[property$=book_name]@content\"),\n    a: X(\"[property$=author]@content\"),\n    k: X(\"[property~=category|status|update_time]@content\\#\\#T\\#\\#&nbsp;&nbsp;\"),\n    l: X(\"[property~=las?test_chapter_name]@content\"),\n    i: X(\"[property$=description]@content\\#\\#简介[：:]\"),\n    c: X(\"[property$=image]@content\")\n});",
      "intro": "i",
      "kind": "k",
      "lastChapter": "l",
      "name": "n"
    },
    "ruleContent": {
      "content": "#nr1@html",
      "nextContentUrl": "text.下一页@href",
      "replaceRegex": "##\\(*第.*页\\)|\\（本章.*阅读\\）"
    },
    "ruleExplore": {
      "author": "text##\\[(.*?)\\](.*?)\\/(.*?)##$3",
      "bookList": "p.line",
      "bookUrl": "a.1@href",
      "coverUrl": "a.1@href\n<js>\nvar id = result.match(/(\\d+)/)[1];\nvar iid = parseInt(id/1000);\n'http://m.xvipxs.net//files/article/image/'+iid+'/'+id+'/'+id+'s.jpg';\n</js>",
      "kind": "text##\\[(.*?)\\](.*?)\\/(.*?)##$1###",
      "name": "text##\\[(.*?)\\](.*?)\\/(.*?)##$2###"
    },
    "ruleReview": {},
    "ruleSearch": {
      "author": "text.作者@text##作者[：:]",
      "bookList": ".block",
      "bookUrl": ".block_txt a.1@href",
      "checkKeyWord": "",
      "coverUrl": "img@src",
      "kind": "text.分类@text##分类[：:]",
      "lastChapter": ".block_txt a.2@text",
      "name": ".block_txt a.1@text"
    },
    "ruleToc": {
      "chapterList": ".chapter li a",
      "chapterName": "text\n@js:result\n.replace(\"••\",\"\")\n.replace(/^(\\d+).第/,'第')\n.replace(/^(正文|VIP章节|最新章节)?(\\s+|_)|[\\(\\{（｛【].*[求含理更谢乐发推票盟补加字Kk\\/].*/g,'')\n.replace(/^(\\d+)[、．]第.+章/,'第$1章')\n.replace(/^(\\d+)、\\d+、/,'第$1章 ')\n.replace(/^(\\d+)、\\d+/,'第$1章')\n.replace(/^(第.+章)\\s?\\d+/,'$1')\n.replace(/^(\\d+)、/,'第$1章 ')\n.replace(/^(第.+章)\\s?第.+章/,'$1')\n.replace(/第\\s(.+)\\s章/,'第$1章')\n.replace(/.*(chapter|Chapter)\\s?(\\d+)\\s?/,'$1 $2 ')\n.replace(/\\(.+\\)/,'')\n.replace(/\\[|。/,'')\n.replace(/第([零一二两三四五六七八九十百千]+)章/g,java.toNumChapter(result))\n##(章)([^\\s]+)(\\s·)##$1 $2$3",
      "chapterUrl": "href",
      "nextTocUrl": "text.下一页@href"
    },
    "searchUrl": "{{cookie.removeCookie(source.getKey())}}/search.php,{\n\"method\": \"POST\",\n\"body\": \"searchkey={{key}}\"\n}",
    "weight": 0
  }
]
