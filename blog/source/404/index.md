title: 404 - Page Not Found
layout: page
comments: false
permalink: /404.html

---
页面将在<span id="jumpTo"></span>秒内自动跳转回[首页]()


曾经有一份真正的页面放在我面前，
我没有珍惜。
等我失去的时候，
我才后悔莫及。
人世间最痛苦的事莫过于此。
如果上天能够给我一个再来一次的机会，

我会对那个页面说三个字：

**<center><font size="25px">四零四</font></cener>**

<script type="text/javascript">
function countDown(secs, surl) {
    var jumpTo = document.getElementById('jumpTo');
    jumpTo.innerHTML = secs;
    if (--secs > 0) {
        setTimeout("countDown(" + secs + ",'" + surl + "')", 1000);
    } else {
        location.href = surl;
    }
}
</script>
<script type="text/javascript">countDown(10,'/');</script>