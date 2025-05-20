# BDG678
<html lang="zh-CN" style="background-color: rgb(145, 149, 163); --status-bar-height: 0px; --top-window-height: 0px; --window-left: 0px; --window-right: 0px; --window-margin: 0px; --window-top: calc(var(--top-window-height) + 0px); --window-bottom: 0px;"><head><link rel="icon" type="image/png" href="/static/manifest/link-logo.png"><meta charset="utf-8"><meta http-equiv="X-UA-Compatible" content="IE=edge"><meta name="apple-mobile-web-app-capable" content="yes"><meta name="apple-mobile-web-app-status-bar-style" content="black"><meta name="apple-mobile-web-app-title" content="98BET"><meta name="application-name" content="98BET"><meta name="format-detection" content="telephone=yes"><meta name="mobile-web-app-capable" content="yes"><meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate"><meta http-equiv="Pragma" content="no-cache"><meta http-equiv="Expires" content="0"><meta property="og:title" content="BG678"><meta property="og:description" content="BG678-Fair and safe, fast withdrawal"><meta property="og:type" content="website"><meta property="og:image" content="/static/manifest/logo-192x192.png"><meta name="twitter:card" content="summary_large_image"><meta name="twitter:title" content="BG678"><meta name="twitter:description" content="BG678-Fair and safe, fast withdrawal"><meta name="twitter:image" content="/static/manifest/logo-192x192.png"><title>BG678</title><script>var coverSupport =
				'CSS' in window &&
				typeof CSS.supports === 'function' &&
				(CSS.supports('top: env(a)') || CSS.supports('top: constant(a)'))
		document.write(
				'<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0' +
				(coverSupport ? ', viewport-fit=cover' : '') +
				'" />'
		)

		document.addEventListener('DOMContentLoaded', function () {
			var splashText = document.getElementById('splash-text')
			splashText.innerText = 'Withdraw fast, safe and stable' // 设置文本内容
			splashText.style.opacity = 1
			var splashTextcopyright = document.getElementById('splash-text-copyright')
			splashTextcopyright.innerText = 'Copyright © All Rights Reserved by BG678.COM' // 设置文本内容
			splashTextcopyright.style.opacity = 1
			document.title = 'BG678'
		})



		if ('serviceWorker' in navigator) {
			// console.log("支持serviceWorker")
			window.addEventListener('load', () => {
				navigator.serviceWorker
						.register('./static/manifest/firebase-messaging-sw.js')
						.then(registration => {})
						.catch(error => {
							// console.log('Service Worker 注册失败:', error);
						})
			})
		} else {
			// console.log("不支持serviceWorker")
		}

		const storedObject = localStorage.getItem('errorUrls')
		window.errorUrls = storedObject ? JSON.parse(storedObject) : {}

		function sendToServiceWorker() {
			if ('serviceWorker' in navigator && navigator.serviceWorker.controller) {
				navigator.serviceWorker.controller.postMessage(
						{
							action: 'errorUrls',
							key: 'errorUrls',
							value: window.errorUrls || {},
						},
						[
							/* transfer list */
						]
				)
			}
		}

		sendToServiceWorker()

		function addErrorUrl(url) {
			if (!window.errorUrls[url]) {
				window.errorUrls[url] = 0
			}
			fetch(url, { cache: 'no-store' })
					.then(response => response.text())
					.then(text => {
						// 处理文本
					})
			window.errorUrls[url] = window.errorUrls[url] + 1
			localStorage.setItem('errorUrls', JSON.stringify(window.errorUrls))

			sendToServiceWorker()
		}

		function reloadScriptWithTimestamp(src) {
			let script = document.createElement('script')
			const time = new Date().getTime()
			script.src = src + `?t=` + time
			script.onerror = function () {
				// console.log('Failed to load script with timestamp')
			}
			document.head.appendChild(script)
		}

		window.onerror = function (message, source, lineno, colno, error) {
			if (source.endsWith('.js') && error instanceof SyntaxError) {
				// reloadScriptWithTimestamp(source); // 重新加载触发错误的脚本
				// 检查错误来源是否包含指定路径
				if (
						source.includes('/static/js/chunk-vendors.') ||
						source.includes('/static/js/index.')
				) {
					// console.log('Error in target script detected. Attempting to reload...')
					reloadScriptWithTimestamp(source)
				} else {
					// console.error('Error in load script detected.', source)
					// 在这里可以执行其他操作
					const loadingDiv = document.getElementById('splash')
					if (loadingDiv) {
						loadingDiv.classList.add('splash-hidden') // 使用类来隐藏元素
					}
					addErrorUrl(source)
				}
			}
			return false // 允许错误继续传播，避免其他全局错误处理器被阻止
		}</script><meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, viewport-fit=cover"><link rel="stylesheet" href="./static/index.2da1efab.css"><link rel="manifest" href="/static/manifest/manifest.json"><style type="text/css">@charset "UTF-8";

/**

 * 这里是uni-app内置的常用样式变量

 *

 * uni-app 官方扩展插件及插件市场（https://ext.dcloud.net.cn）上很多三方插件均使用了这些样式变量

 * 如果你是插件开发者，建议你使用scss预处理，并在插件代码中直接使用这些变量（无需 import 这个文件），方便用户通过搭积木的方式开发整体风格一致的App

 *

 */

/**

 * 如果你是App开发者（插件使用者），你可以通过修改这些变量来定制自己的插件主题，实现自定义主题功能

 *

 * 如果你的项目同样使用了scss预处理，你也可以直接在你的 scss 代码中使用如下变量，同时无需 import 这个文件

 */.flex-col{display:flex;display:-webkit-flex;flex-direction:column}.flex-row{display:flex;display:-webkit-flex;flex-direction:row}.justify-start{display:flex;display:-webkit-flex;justify-content:flex-start}.justify-center{display:flex;display:-webkit-flex;justify-content:center}.justify-end{display:flex;display:-webkit-flex;justify-content:flex-end}.justify-evenly{display:flex;display:-webkit-flex;justify-content:space-evenly}.justify-around{display:flex;display:-webkit-flex;justify-content:space-around}.justify-between{display:flex;display:-webkit-flex;justify-content:space-between}.align-start{display:flex;display:-webkit-flex;align-items:flex-start;-webkit-align-items:flex-start}.align-center{display:flex;display:-webkit-flex;align-items:center;-webkit-align-items:center}.align-end{display:flex;display:-webkit-flex;align-items:flex-end;-webkit-align-items:flex-end}.defaultbg{background-position:50%;background-repeat:no-repeat;background-size:100% 100%}

/* 颜色变量 */

/* 行为相关颜色 */

/* 文字基本颜色 */

/* 背景颜色 */

/* 边框颜色 */

/* 尺寸变量 */

/* 文字尺寸 */

/* 图片尺寸 */

/* Border Radius */

/* 水平间距 */

/* 垂直间距 */

/* 透明度 */

/* 文章场景相关 */

/* 注意要写在第一行，同时给style标签加入lang="scss"属性 */.u-line-1{display:-webkit-box!important;overflow:hidden;text-overflow:ellipsis;word-break:break-all;-webkit-line-clamp:1;-webkit-box-orient:vertical!important}.u-line-2{display:-webkit-box!important;overflow:hidden;text-overflow:ellipsis;word-break:break-all;-webkit-line-clamp:2;-webkit-box-orient:vertical!important}.u-line-3{display:-webkit-box!important;overflow:hidden;text-overflow:ellipsis;word-break:break-all;-webkit-line-clamp:3;-webkit-box-orient:vertical!important}.u-line-4{display:-webkit-box!important;overflow:hidden;text-overflow:ellipsis;word-break:break-all;-webkit-line-clamp:4;-webkit-box-orient:vertical!important}.u-line-5{display:-webkit-box!important;overflow:hidden;text-overflow:ellipsis;word-break:break-all;-webkit-line-clamp:5;-webkit-box-orient:vertical!important}.u-border{border-width:.5px!important;border-color:#dadbde!important;border-style:solid}.u-border-top{border-top-width:.5px!important;border-color:#dadbde!important;border-top-style:solid}.u-border-left{border-left-width:.5px!important;border-color:#dadbde!important;border-left-style:solid}.u-border-right{border-right-width:.5px!important;border-color:#dadbde!important;border-right-style:solid}.u-border-bottom{border-bottom-width:.5px!important;border-color:#dadbde!important;border-bottom-style:solid}.u-border-top-bottom{border-top-width:.5px!important;border-bottom-width:.5px!important;border-color:#dadbde!important;border-top-style:solid;border-bottom-style:solid}.u-reset-button{padding:0;background-color:initial;font-size:inherit;line-height:inherit;color:inherit}.u-reset-button::after{border:none}.u-hover-class{opacity:.7}.u-primary-light{color:#ecf5ff}.u-warning-light{color:#fdf6ec}.u-success-light{color:#f5fff0}.u-error-light{color:#fef0f0}.u-info-light{color:#f4f4f5}.u-primary-light-bg{background-color:#ecf5ff}.u-warning-light-bg{background-color:#fdf6ec}.u-success-light-bg{background-color:#f5fff0}.u-error-light-bg{background-color:#fef0f0}.u-info-light-bg{background-color:#f4f4f5}.u-primary-dark{color:#398ade}.u-warning-dark{color:#f1a532}.u-success-dark{color:#53c21d}.u-error-dark{color:#e45656}.u-info-dark{color:#767a82}.u-primary-dark-bg{background-color:#398ade}.u-warning-dark-bg{background-color:#f1a532}.u-success-dark-bg{background-color:#53c21d}.u-error-dark-bg{background-color:#e45656}.u-info-dark-bg{background-color:#767a82}.u-primary-disabled{color:#9acafc}.u-warning-disabled{color:#f9d39b}.u-success-disabled{color:#a9e08f}.u-error-disabled{color:#f7b2b2}.u-info-disabled{color:#c4c6c9}.u-primary{color:#3c9cff}.u-warning{color:#f9ae3d}.u-success{color:#5ac725}.u-error{color:#f56c6c}.u-info{color:#909399}.u-primary-bg{background-color:#3c9cff}.u-warning-bg{background-color:#f9ae3d}.u-success-bg{background-color:#5ac725}.u-error-bg{background-color:#f56c6c}.u-info-bg{background-color:#909399}.u-main-color{color:#303133}.u-content-color{color:#606266}.u-tips-color{color:#909193}.u-light-color{color:#c0c4cc}.u-safe-area-inset-top{padding-top:0;padding-top:constant(safe-area-inset-top);padding-top:env(safe-area-inset-top)}.u-safe-area-inset-right{padding-right:0;padding-right:constant(safe-area-inset-right);padding-right:env(safe-area-inset-right)}.u-safe-area-inset-bottom{padding-bottom:0;padding-bottom:constant(safe-area-inset-bottom);padding-bottom:env(safe-area-inset-bottom)}.u-safe-area-inset-left{padding-left:0;padding-left:constant(safe-area-inset-left);padding-left:env(safe-area-inset-left)}uni-toast{z-index:10090}uni-toast .uni-toast{z-index:10090}::-webkit-scrollbar{display:none;width:0;height:0}.show-scrollbar::-webkit-scrollbar{display:block;

  /* 或 initial，根据需要选择 */width:12px;

  /* 滚动条宽度 */height:12px;

  /* 滚动条高度，对于垂直滚动条 */background-color:#f1f1f1

  /* 滚动条背景颜色 */}.show-scrollbar::-webkit-scrollbar-thumb{background-color:#c1c1c1;

  /* 滚动条拖动部分的颜色 */border-radius:6px

  /* 滚动条圆角 */}:root{--max-width:384px}html,

body{width:100%;max-width:var(--max-width);margin:0 auto;font-family:arial}uni-page-body{

  /* height: 100%; */}

/* 针对没有定位的 */.maxWidth{max-width:var(--max-width);margin:0 auto}

/* 针对有定位的 */.positionMaxWidth{max-width:var(--max-width);left:50%;-webkit-transform:translateX(-50%);transform:translateX(-50%)}.lrPadding{padding:0 11px}.tabbar{max-width:var(--max-width);left:50%!important;-webkit-transform:translateX(-50%);transform:translateX(-50%)}.tabbar, .shareComp{max-width:var(--max-width);left:50%!important;-webkit-transform:translateX(-50%);transform:translateX(-50%)}.relative{position:relative}uni-view{box-sizing:border-box}.flex{display:flex;justify-content:space-between;align-items:center}.listNoMore{text-align:center;color:#777;margin-bottom:9px}.column{flex-direction:column}.componentMaxWidth uni-view{max-width:var(--max-width)}a{text-decoration:none}@media screen and (max-width:var(--max-width)){html,

  body{max-width:var(--max-width)}uni-view{box-sizing:border-box}.positionMaxWidth{max-width:var(--max-width);left:50%;-webkit-transform:translateX(-50%);transform:translateX(-50%)}.maxWidth{max-width:var(--max-width);margin:0 auto}

  /* 其他需要针对小屏幕优化的样式 */}

/*每个页面公共css */uni-page-body{background:#f7f8ff;padding-top:0px}body{background:#f7f8ff}.content{display:flex;flex-direction:column;gap:7px;padding-inline:11px;padding-bottom:76px}.van-dialog{top:45%;width:320px;overflow:hidden;font-size:16px;background:#fff;border-radius:16px;-webkit-backface-visibility:hidden;backface-visibility:hidden;transition:.3s;transition-property:opacity,-webkit-transform;transition-property:transform,opacity;transition-property:transform,opacity,-webkit-transform}.van-overlay{position:fixed;top:0;z-index:1;width:100%;height:100%;background:rgba(0,0,0,.7);left:50%;-webkit-transform:translateX(-50%);transform:translateX(-50%)}.van-overflow-hidden{overflow:hidden!important}.van-popup.van-popup--bottom{left:50%;-webkit-transform:translateX(-50%);transform:translateX(-50%)}.van-popup{position:fixed;overflow-y:auto;box-sizing:border-box;max-height:100%;background:#1c1c1e;transition:-webkit-transform .3s;transition:transform .3s;transition:transform .3s,-webkit-transform .3s}.van-popup--center{top:50%;right:0;left:0;margin:0 auto;width:-webkit-fit-content;width:fit-content;max-width:calc(100% - 15px);-webkit-transform:translateY(-50%);transform:translateY(-50%)}.van-popup--center.van-popup--round{border-radius:7px}.van-popup--top{top:0;left:0;width:100%}.van-popup--top.van-popup--round{border-radius:0 0 7px 7px}.van-popup--right{top:50%;right:0;-webkit-transform:translate3d(0,-50%,0);transform:translate3d(0,-50%,0)}.van-popup--right.van-popup--round{border-radius:7px 0 0 7px}.van-popup--bottom{bottom:0;left:0;width:100%}.van-popup--bottom.van-popup--round{border-radius:7px 7px 0 0}.van-popup--left{top:50%;left:0;-webkit-transform:translate3d(0,-50%,0);transform:translate3d(0,-50%,0)}.van-popup--left.van-popup--round{border-radius:0 7px 7px 0}.van-popup-slide-top-enter-active,

.van-popup-slide-left-enter-active,

.van-popup-slide-right-enter-active,

.van-popup-slide-bottom-enter-active{transition-timing-function:ease-out}.van-popup-slide-top-leave-active,

.van-popup-slide-left-leave-active,

.van-popup-slide-right-leave-active,

.van-popup-slide-bottom-leave-active{transition-timing-function:ease-in}.van-popup-slide-top-enter-from,

.van-popup-slide-top-leave-active{-webkit-transform:translate3d(0,-100%,0);transform:translate3d(0,-100%,0)}.van-popup-slide-right-enter-from,

.van-popup-slide-right-leave-active{-webkit-transform:translate3d(100%,-50%,0);transform:translate3d(100%,-50%,0)}.van-popup-slide-bottom-enter-from,

.van-popup-slide-bottom-leave-active{-webkit-transform:translate3d(0,100%,0);transform:translate3d(0,100%,0)}.van-popup-slide-left-enter-from,

.van-popup-slide-left-leave-active{-webkit-transform:translate3d(-100%,-50%,0);transform:translate3d(-100%,-50%,0)}.van-popup__close-icon{position:absolute;z-index:1;color:#c8c9cc;font-size:10px}.van-popup__close-icon--top-left{top:7px;left:7px}.van-popup__close-icon--top-right{top:7px;right:7px}.van-popup__close-icon--bottom-left{bottom:7px;left:7px}.van-popup__close-icon--bottom-right{right:7px;bottom:7px}.van-row{display:flex;flex-wrap:wrap}.van-col{display:block;box-sizing:border-box;min-height:1px}.van-col--1{flex:0 0 4.16666667%;max-width:4.16666667%}.van-col--offset-1{margin-left:4.16666667%}.van-col--2{flex:0 0 8.33333333%;max-width:8.33333333%}.van-col--offset-2{margin-left:8.33333333%}.van-col--3{flex:0 0 12.5%;max-width:12.5%}.van-col--offset-3{margin-left:12.5%}.van-col--4{flex:0 0 16.66666667%;max-width:16.66666667%}.van-col--offset-4{margin-left:16.66666667%}.van-col--5{flex:0 0 20.83333333%;max-width:20.83333333%}.van-col--offset-5{margin-left:20.83333333%}.van-col--6{flex:0 0 25%;max-width:25%}.van-col--offset-6{margin-left:25%}.van-col--7{flex:0 0 29.16666667%;max-width:29.16666667%}.van-col--offset-7{margin-left:29.16666667%}.van-col--8{flex:0 0 33.33333333%;max-width:33.33333333%}.van-col--offset-8{margin-left:33.33333333%}.van-col--9{flex:0 0 37.5%;max-width:37.5%}.van-col--offset-9{margin-left:37.5%}.van-col--10{flex:0 0 41.66666667%;max-width:41.66666667%}.van-col--offset-10{margin-left:41.66666667%}.van-col--11{flex:0 0 45.83333333%;max-width:45.83333333%}.van-col--offset-11{margin-left:45.83333333%}.van-col--12{flex:0 0 50%;max-width:50%}.van-col--offset-12{margin-left:50%}.van-col--13{flex:0 0 54.16666667%;max-width:54.16666667%}.van-col--offset-13{margin-left:54.16666667%}.van-col--14{flex:0 0 58.33333333%;max-width:58.33333333%}.van-col--offset-14{margin-left:58.33333333%}.van-col--15{flex:0 0 62.5%;max-width:62.5%}.van-col--offset-15{margin-left:62.5%}.van-col--16{flex:0 0 66.66666667%;max-width:66.66666667%}.van-col--offset-16{margin-left:66.66666667%}.van-col--17{flex:0 0 70.83333333%;max-width:70.83333333%}.van-col--offset-17{margin-left:70.83333333%}.van-col--18{flex:0 0 75%;max-width:75%}.van-col--offset-18{margin-left:75%}.van-col--19{flex:0 0 79.16666667%;max-width:79.16666667%}.van-col--offset-19{margin-left:79.16666667%}.van-col--20{flex:0 0 83.33333333%;max-width:83.33333333%}.van-col--offset-20{margin-left:83.33333333%}.van-col--21{flex:0 0 87.5%;max-width:87.5%}.van-col--offset-21{margin-left:87.5%}.van-col--22{flex:0 0 91.66666667%;max-width:91.66666667%}.van-col--offset-22{margin-left:91.66666667%}.van-col--23{flex:0 0 95.83333333%;max-width:95.83333333%}.van-col--offset-23{margin-left:95.83333333%}.van-col--24{flex:0 0 100%;max-width:100%}.van-col--offset-24{margin-left:100%}.infiniteScroll{min-height:96px;border-radius:5px}.infiniteScroll__loading{width:100%;min-height:26px;margin-top:auto;margin-bottom:14px;color:#999;font-size:13px;text-align:center}.infiniteScroll__loading .van-loading{text-align:center;z-index:999}.empty__container{width:100%;height:100%;display:flex;flex-direction:column;align-items:center}.empty__container uni-image{width:144px;height:133px;margin-bottom:9px}.empty__container uni-text{color:#acafc2;font-size:12px}.preload-image{width:1px;height:1px;opacity:.01}</style><style type="text/css">@charset "UTF-8";

/**

 * 这里是uni-app内置的常用样式变量

 *

 * uni-app 官方扩展插件及插件市场（https://ext.dcloud.net.cn）上很多三方插件均使用了这些样式变量

 * 如果你是插件开发者，建议你使用scss预处理，并在插件代码中直接使用这些变量（无需 import 这个文件），方便用户通过搭积木的方式开发整体风格一致的App

 *

 */

/**

 * 如果你是App开发者（插件使用者），你可以通过修改这些变量来定制自己的插件主题，实现自定义主题功能

 *

 * 如果你的项目同样使用了scss预处理，你也可以直接在你的 scss 代码中使用如下变量，同时无需 import 这个文件

 */.flex-col[data-v-739fa333]{display:flex;display:-webkit-flex;flex-direction:column}.flex-row[data-v-739fa333]{display:flex;display:-webkit-flex;flex-direction:row}.justify-start[data-v-739fa333]{display:flex;display:-webkit-flex;justify-content:flex-start}.justify-center[data-v-739fa333]{display:flex;display:-webkit-flex;justify-content:center}.justify-end[data-v-739fa333]{display:flex;display:-webkit-flex;justify-content:flex-end}.justify-evenly[data-v-739fa333]{display:flex;display:-webkit-flex;justify-content:space-evenly}.justify-around[data-v-739fa333]{display:flex;display:-webkit-flex;justify-content:space-around}.justify-between[data-v-739fa333]{display:flex;display:-webkit-flex;justify-content:space-between}.align-start[data-v-739fa333]{display:flex;display:-webkit-flex;align-items:flex-start;-webkit-align-items:flex-start}.align-center[data-v-739fa333]{display:flex;display:-webkit-flex;align-items:center;-webkit-align-items:center}.align-end[data-v-739fa333]{display:flex;display:-webkit-flex;align-items:flex-end;-webkit-align-items:flex-end}.defaultbg[data-v-739fa333]{background-position:50%;background-repeat:no-repeat;background-size:100% 100%}

/* 颜色变量 */

/* 行为相关颜色 */

/* 文字基本颜色 */

/* 背景颜色 */

/* 边框颜色 */

/* 尺寸变量 */

/* 文字尺寸 */

/* 图片尺寸 */

/* Border Radius */

/* 水平间距 */

/* 垂直间距 */

/* 透明度 */

/* 文章场景相关 */.defaultFlex[data-v-739fa333], .float-ball-movable-area[data-v-739fa333], .float-ball[data-v-739fa333]{display:flex;align-items:center;justify-content:center}.float-ball-wrap[data-v-739fa333]{position:fixed;bottom:0;z-index:9999;width:100%;height:100vh;pointer-events:none;overflow:hidden}.float-ball-movable-area[data-v-739fa333]{position:relative;top:0;left:0;z-index:16;width:100%;height:100%}.float-ball[data-v-739fa333]{flex:1;pointer-events:auto;width:auto;height:auto;z-index:16;border-radius:50%;position:absolute!important}.default-icon-hover[data-v-739fa333]{opacity:.6}</style><style type="text/css">@charset "UTF-8";

/**

 * 这里是uni-app内置的常用样式变量

 *

 * uni-app 官方扩展插件及插件市场（https://ext.dcloud.net.cn）上很多三方插件均使用了这些样式变量

 * 如果你是插件开发者，建议你使用scss预处理，并在插件代码中直接使用这些变量（无需 import 这个文件），方便用户通过搭积木的方式开发整体风格一致的App

 *

 */

/**

 * 如果你是App开发者（插件使用者），你可以通过修改这些变量来定制自己的插件主题，实现自定义主题功能

 *

 * 如果你的项目同样使
