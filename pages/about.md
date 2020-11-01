---
layout: page
title: About
description: 鎵撶爜鏀瑰彉涓栫晫
keywords: Zhuang Ma, 椹�澹�
comments: true
menu: 鍏充簬
permalink: /about/
---

鎴戞槸椹�澹�锛岀爜鑰岀敓锛岀爜鑰岀珛銆�

浠版厱銆屼紭闆呯紪鐮佺殑鑹烘湳銆嶃€�

鍧氫俊鐔熻兘鐢熷阀锛屽姫鍔涙敼鍙樹汉鐢熴€�

## 鑱旂郴

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}锛�<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
寰�淇″叕浼楀彿锛�<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ assets_base_url }}/assets/images/qrcode.jpg" alt="闂烽獨鐨勭▼搴忓憳" />
</li>
{% endif %}
</ul>


## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
