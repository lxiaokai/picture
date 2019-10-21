# picture
picture
//js脚本
NSString *jScript = @"var meta = document.createElement('meta'); meta.setAttribute('name', 'viewport'); meta.setAttribute('content', 'width=device-width'); document.getElementsByTagName('head')[0].appendChild(meta);";
//注入
WKUserScript *wkUScript = [[WKUserScript alloc] initWithSource:jScript injectionTime:WKUserScriptInjectionTimeAtDocumentEnd forMainFrameOnly:YES];
WKUserContentController *wkUController = [[WKUserContentController alloc] init]; 
[wkUController addUserScript:wkUScript];
//配置对象
WKWebViewConfiguration *wkWebConfig = [[WKWebViewConfiguration alloc] init];
wkWebConfig.userContentController = wkUController;
