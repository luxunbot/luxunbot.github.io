## 鲁迅曾经说过：

> 我以为绝望而反抗者难，比因希望而战斗者更勇猛，更悲壮。

<button>再来一句</button>

## Usage

request
```http
GET /v1/quotes/
```
response
```json
{
  "quote": "这回总对了吧"
}
```

<script>
  function luxun() {
    return new Promise(function (res, rej) {
      fetch('https://api.baishu.tk/v1/quotes/')
        .then(res => res.json())
        .then(json => res(json.quote))
        .catch(rej);
    });
  }
  
  window.onload = function() {
    var btn = document.querySelector('button');
    var quote = document.querySelector('blockquote p');
 
    luxun().then(data => quote.textContent = data);
    btn.addEventListener('click', function(e) {
      luxun().then(data => quote.textContent = data)
    });
  }
</script>
