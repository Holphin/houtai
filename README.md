
<!DOCTYPE html>
<html>
<head>
  <title>Sugar</title>
  <meta charset="utf-8"/>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <meta http-equiv="X-UA-Compatible" content="IE=Edge"/>
  <meta name="keywords" content="Sugar,数据可视化,报表可视化编辑">
  <meta name="author" content="Baidu,Sugar">
  <meta name="renderer" content="webkit">
  <meta name="force-rendering" content="webkit"/>
  <meta name="csrf-token" content="SxWPcIId-oofhfwLz-1ICDw-gbRN6JVukeBg"/>
  <meta name="sugar-company" content=""/>
  <link type="image/x-icon" rel="shortcut icon" href="/static/favicon-new.ico"/>

    <link rel="stylesheet" type="text/css" href="/static/sugar/pkg/lib_c2f4822.css" />
    <link rel="stylesheet" type="text/css" href="/static/sugar/pkg/app_86e5e4c.css" />
</head>
<body>
  <div id="sugar-root"></div>
  <script type="text/javascript">
    window.sugarConfig = {"notifyPosition":"tr","name":"Sugar","selfIpWhiteList":"14.215.188.4/25,111.45.0.0/22","deployType":"saas","shareSourceDomain":"https://sugar.baidubce.com","enableTunnel":true};
    var browserNotSupport = false;
    var ua = navigator.userAgent;
    if (!/(chrome|webkit|safari|firefox)/i.test(ua) || /\bEdge\//.test(ua) || /\bOPR\//.test(ua)) {
      browserNotSupport = true;
      document.getElementById('sugar-root').innerHTML = '<p style="text-align:center; margin-top:10px; font-size:16px;">系统不支持您当前内核的浏览器，建议使用Chrome浏览器</p>';
    }
    // polyfill Object.assign
    if (typeof Object.assign != 'function') {
      // Must be writable: true, enumerable: false, configurable: true
      Object.defineProperty(Object, "assign", {
        value: function assign(target, varArgs) { // .length of function is 2
          'use strict';
          if (target == null) { // TypeError if undefined or null
            throw new TypeError('Cannot convert undefined or null to object');
          }

          var to = Object(target);

          for (var index = 1; index < arguments.length; index++) {
            var nextSource = arguments[index];

            if (nextSource != null) { // Skip over if undefined or null
              for (var nextKey in nextSource) {
                // Avoid bugs when hasOwnProperty is shadowed
                if (Object.prototype.hasOwnProperty.call(nextSource, nextKey)) {
                  to[nextKey] = nextSource[nextKey];
                }
              }
            }
          }
          return to;
        },
        writable: true,
        configurable: true
      });
    }
    // polyfill Array.find
    if (!Array.prototype.find) {
      Object.defineProperty(Array.prototype, 'find', {
        value: function(predicate) {
        // 1. Let O be ? ToObject(this value).
          if (this == null) {
            throw new TypeError('"this" is null or not defined');
          }

          var o = Object(this);

          // 2. Let len be ? ToLength(? Get(O, "length")).
          var len = o.length >>> 0;

          // 3. If IsCallable(predicate) is false, throw a TypeError exception.
          if (typeof predicate !== 'function') {
            throw new TypeError('predicate must be a function');
          }

          // 4. If thisArg was supplied, let T be thisArg; else let T be undefined.
          var thisArg = arguments[1];

          // 5. Let k be 0.
          var k = 0;

          // 6. Repeat, while k < len
          while (k < len) {
            // a. Let Pk be ! ToString(k).
            // b. Let kValue be ? Get(O, Pk).
            // c. Let testResult be ToBoolean(? Call(predicate, T, « kValue, k, O »)).
            // d. If testResult is true, return kValue.
            var kValue = o[k];
            if (predicate.call(thisArg, kValue, k, o)) {
              return kValue;
            }
            // e. Increase k by 1.
            k++;
          }

          // 7. Return undefined.
          return undefined;
        }
      });
    }
  </script>

<script type="text/javascript" src="/static/sugar/static/mod_6919661.js"></script>
<script type="text/javascript" src="/static/sugar/pkg/lib_b598128.js"></script>
<script type="text/javascript" src="/static/sugar/pkg/app_5348065.js"></script>
<script src="//api.map.baidu.com/api?v=3.0&ak=pWKhO4mQb4s9MWqP0siqzGlZW5aeqG90"></script>
<script type="text/javascript" src="/static/sugar/static/js/cyberplayer/cyberplayer.js"></script>
<script type="text/javascript" src="/static/sugar/pkg/videolib_7310b86.js"></script>
<script type="text/javascript">
    (function () {
      sugarConfig.companyName = "百度";
      sugarConfig.expiredTime = 473351999;
      sugarConfig.sTime = 260673871;
      sugarConfig.loginType = "cloud";

      var initialState = {
        user: {
          current: {}
        },
        company: {
          info: {"config":{}},
          admins: [],
          myCompanys: []
        }
      };
      window.sugarAjaxTimeout = 60;
      if (sugarConfig.deployType === 'private') {
        window.sugarAjaxTimeout = (parseInt(initialState.company.info.config.sqlTimeout, 10) || 50) + 10;
        if (initialState.company.info.config.backgroudColor) {
          var bk = initialState.company.info.config.backgroudColor;
          document.write("<style>html{background-color: " + bk + " !important;}.app:before{background-color: " + bk + " !important;}</style>")
        }
      }
      // 打开新的url，并且附带上当前页面url中的参数，conditions参数会做merge，blank参数表示是否新打开tab页，默认在当前页面打开
      function _sugarOpenUrl(url, blank) {
        var pathAndSearch = url.split('?');
        var path = pathAndSearch[0];
        var urlSearchArr = (pathAndSearch[1] || '').split('&');
        var serchArr = [];
        var conditions = {};
        for (var index = 0; index < urlSearchArr.length; index++) {
          var item = urlSearchArr[index];
          var tmpMatch = item.match(/\bconditions\=(.*)/);
          if (tmpMatch) {
            try {
              conditions = JSON.parse(decodeURIComponent(tmpMatch[1]));
            } catch (e) {
              conditions = {};
            }
          } else {
            serchArr.push(item);
          }
        }

        var currentSearch = window.location.search.split('&');
        var currentConditions = {};
        for (var i = 0; i < currentSearch.length; ++i) {
          var tmpMatch = currentSearch[i].match(/\bconditions\=(.*)/);
          if (tmpMatch) {
            try {
              currentConditions = JSON.parse(decodeURIComponent(tmpMatch[1]));
              for (var key in conditions) {
                if (conditions.hasOwnProperty(key)) {
                  currentConditions[key] = conditions[key];
                }
              }
            } catch (e) {}
          } else {
            serchArr.push(currentSearch[i]);
          }
        }

        serchArr.push('conditions=' + encodeURIComponent(JSON.stringify(currentConditions)));
        var newUrl = path;
        if (serchArr.length) {
          newUrl += '?' + serchArr.join('&');
        }
        if (blank) {
          window.open(newUrl);
        } else {
          window.location.href = newUrl;
        }
      }
      window.sugarOpenUrl = _sugarOpenUrl;

      if (!window.browserNotSupport) {
        require('sugar:index.tsx').bootstrap(document.getElementById('sugar-root'), initialState);
      }
    })();
    var _hmt = _hmt || [];
    (function() {
      if (window.sugarConfig.deployType === 'saas') {
        var hm = document.createElement("script");
        hm.src = "https://hm.baidu.com/hm.js?0369a83cfe6c3d97357eea08cc40e92f";
        var s = document.getElementsByTagName("script")[0];
        s.parentNode.insertBefore(hm, s);

        // sentry
        window.SENTRY_SDK = {
          url: 'https://bce.bdstatic.com/fex/ravenjs/3.26.4/raven.min.js',
          dsn: 'https://db4946a394c2479f8438528534412548@sentry.io/1282846',
          options: {
            release: '1.3.0'
          }
        }
        ;(function(a,b,g,e,h){var k=a.SENTRY_SDK,f=function(a){f.data.push(a)};f.data=[];var l=a[e];a[e]=function(c,b,e,d,h){f({e:[].slice.call(arguments)});l&&l.apply(a,arguments)};var m=a[h];a[h]=function(c){f({p:c.reason});m&&m.apply(a,arguments)};var n=b.getElementsByTagName(g)[0];b=b.createElement(g);b.src=k.url;b.crossorigin="anonymous";b.addEventListener("load",function(){try{a[e]=l;a[h]=m;var c=f.data,b=a.Raven;b.config(k.dsn,k.options).install();var g=a[e];if(c.length)for(var d=0;d<c.length;d++)c[d].e?g.apply(b.TraceKit,c[d].e):c[d].p&&b.captureException(c[d].p)}catch(p){console.log(p)}});n.parentNode.insertBefore(b,n)})(window,document,"script","onerror","onunhandledrejection");
      }
    })();
  </script>
</body>
</html>
