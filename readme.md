# readme

Automatically get readings and markdown fmt text @https://www3 nhk.or.jp/news/easy/

```js

vocab = {}
$('ruby').each((i,e)=>{
    let read = $(e).children("rt").text()
    let word = e.textContent.split(read)
    vocab[word] = read;
})

$(".hide-sp").click()
$("rt").html("")
arr = [
    "# 2022",
    "# " + $(".article-main__title").text().trim(),
    "# " +$(".article-main__date").text().trim(),
    window.location.href,
    $(".article-main__body").text().trim()
]


console.log(arr.join("\n"))
vocstr = ""
Object.keys(vocab).forEach((e,i)=>{
    vocstr += [e, vocab[e]].join(": ") + "\n"
})
except = `災害,: さいがい
気,: き
外国人,: がいこくじん
皆,: みな
小学生,: しょうがくせい
中学生,: ちゅうがくせい
伝,: つた`
console.log("```\n"+vocstr.replace(except,"")+"\n```")
// except = `災害,: さいがい
// 気,: き`
```
