# ScrapingBrowser

- [ScrapingBrowser.NavigateToPage C# (CSharp) Code Examples - HotExamples](https://csharp.hotexamples.com/examples/-/ScrapingBrowser/NavigateToPage/php-scrapingbrowser-navigatetopage-method-examples.html)
- [Scraping data dynamically generated by JavaScript in html document using C#](https://stackoverflow.com/questions/24130650/scraping-data-dynamically-generated-by-javascript-in-html-document-using-c-sharp)

## Demo

### By JavaScript in html document

```c#
- [WebBrowser Control (Internet Explorer)](https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))

Uri uri = new Uri("http://www.somewebsite.com/somepage.htm");

webBrowserControl.AllowNavigation = true;
// optional but I use this because it stops javascript errors breaking your scraper
webBrowserControl.ScriptErrorsSuppressed = true;
// you want to start scraping after the document is finished loading so do it in the function you pass to this handler
webBrowserControl.DocumentCompleted += new WebBrowserDocumentCompletedEventHandler(webBrowserControl_DocumentCompleted);
webBrowserControl.Navigate(uri);

private void webBrowserControl_DocumentCompleted(object sender, WebBrowserDocumentCompletedEventArgs e)
{
    HtmlElementCollection divs = webBrowserControl.Document.GetElementsByTagName("div");

    foreach (HtmlElement div in divs)
    {
        //do something
    }
}
```
