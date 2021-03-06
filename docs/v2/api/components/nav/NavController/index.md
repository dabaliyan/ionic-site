---
layout: "v2_fluid/docs_base"
version: "2.0.0"
versionHref: "/docs/v2"
path: ""
category: api
id: "{{NavController | slugify}}"
title: "NavController"
header_sub_title: "Class in module "
doc: "NavController"
docType: "class"
---


<div class="improve-docs">
  <a href='http://github.com/driftyco/ionic2/tree/master/ionic/components/nav/nav-controller.ts#L9'>
    View Source
  </a>
  &nbsp;
  <a href='http://github.com/driftyco/ionic2/edit/master/ionic/components/nav/nav-controller.ts#L9'>
    Improve this doc
  </a>
</div>




<h1 class="api-title">

  NavController



</h1>





<p><em>For examples on the basic usage of NavController, check out the <a href="../../../../components/#navigation">Navigation section</a>
of the Component docs.</em></p>
<p>NavController is the base class for navigation controller components like
<a href="../Nav/"><code>Nav</code></a> and <a href="../../Tabs/Tab/"><code>Tab</code></a>. You use navigation controllers
to navigate to <a href="#creating_pages">pages</a> in your app. At a basic level, a
navigation controller is an array of pages representing a particular history
(of a Tab for example). This array can be manipulated to navigate throughout
an app by pushing and popping pages or inserting and removing them at
arbitrary locations in history.</p>
<p>The current page is the last one in the array, or the top of the stack if we
think of it that way.  <a href="#push">Pushing</a> a new page onto the top of the
navigation stack causes the new page to be animated in, while <a href="#pop">popping</a>
the current page will navigate to the previous page in the stack.</p>
<p>Unless you are using a directive like <a href="../NavPush/">NavPush</a>, or need a
specific NavController, most times you will inject and use a reference to the
nearest NavController to manipulate the navigation stack.</p>
<p><h3 id="injecting_nav_controller">Injecting NavController</h3>
Injecting NavController will always get you an instance of the nearest
NavController, regardless of whether it is a Tab or a Nav.</p>
<p>Behind the scenes, when Ionic instantiates a new NavController, it creates an
injector with NavController bound to that instance (usually either a Nav or
Tab) and adds the injector to its own providers.  For more information on
providers and dependency injection, see <a href="">Providers and DI</a>.</p>
<pre><code class="lang-ts">// class NavController
this.providers = Injector.resolve([
  provide(NavController, {useValue: this})
]);
</code></pre>
<p>Instead, you can inject NavController and know that it is the correct
navigation controller for most situations (for more advanced situations, see
<a href="../../Menu/Menu/">Menu</a> and <a href="../../Tab/Tab/">Tab</a>).</p>
<pre><code class="lang-ts">class MyComponent {
  constructor(nav: NavController) {
    this.nav = nav;
  }
}
</code></pre>
<p><h2 id="creating_pages">Page creation</h2>
<em>For more information on the <code>@Page</code> decorator see the <a href="../../../config/Page/">@Page API
reference</a>.</em></p>
<p>Pages are created when they are added to the navigation stack.  For methods
like <a href="#push">push()</a>, the NavController takes any component class that is
decorated with @Page as its first argument.  The NavController then
<a href="">compiles</a> that component, adds it to the DOM in a similar fashion to
Angular&#39;s <a href="https://angular.io/docs/js/latest/api/core/DynamicComponentLoader-interface.html">DynamicComponentLoader</a>,
and animates it into view.</p>
<p>By default, pages are cached and left in the DOM if they are navigated away
from but still in the navigation stack (the exiting page on a <code>push()</code> for
example).  They are destroyed when removed from the navigation stack (on
<a href="#pop">pop()</a> or <a href="#setRoot">setRoot()</a>).</p>
<p><h2 id="Lifecycle">Lifecycle events</h2>
Lifecycle events are fired during various stages of navigation.  They can be
defined in any <code>@Page</code> decorated component class.</p>
<pre><code class="lang-ts">@Page({
  template: &#39;Hello World&#39;
})
class HelloWorld {
  onPageLoaded() {
    console.log(&quot;I&#39;m alive!&quot;);
  }
}
</code></pre>
<ul>
<li><code>onPageLoaded</code> - Runs when the page has loaded. This event only happens once per page being created and added to the DOM. If a page leaves but is cached, then this event will not fire again on a subsequent viewing. The <code>onPageLoaded</code> event is good place to put your setup code for the page.</li>
<li><code>onPageWillEnter</code> - Runs when the page is about to enter and become the active page.</li>
<li><code>onPageDidEnter</code> - Runs when the page has fully entered and is now the active page. This event will fire, whether it was the first load or a cached page.</li>
<li><code>onPageWillLeave</code> - Runs when the page is about to leave and no longer be the active page.</li>
<li><code>onPageDidLeave</code> - Runs when the page has finished leaving and is no longer the active page.</li>
<li><code>onPageWillUnload</code> - Runs when the page is about to be destroyed and have its elements removed.</li>
<li><code>onPageDidUnload</code> - Runs after the page has been destroyed and its elements have been removed.</li>
</ul>


<h1 class="class export">NavController <span class="type">class</span></h1>
<p class="module">exported from <a href='undefined'>ionic/ionic</a><br/>
defined in <a href="https://github.com/driftyco/ionic2/tree/master/ionic/components/nav/nav-controller.ts#L10-L1074">ionic/components/nav/nav-controller.ts (line 10)</a>
</p>
## Members

<div id="push"></div>
<h2>
  <code>push(componentType, params, opts)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        componentType
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
    <tr>
      <td>
        params
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
    <tr>
      <td>
        opts
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>Promise</code> TODO




<div id="pop"></div>
<h2>
  <code>pop(opts)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        opts
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>Promise</code> TODO




<div id="popToRoot"></div>
<h2>
  <code>popToRoot(opts)</code>

</h2>

Pop to the root view.



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        opts
        
        
      </td>
      <td>
        
  
      </td>
      <td>
        <p>extra animation options</p>

        
      </td>
    </tr>
    
  </tbody>
</table>









<div id="insert"></div>
<h2>
  <code>insert(componentType, index)</code>

</h2>

Inserts a view into the nav stack at the specified index.



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        componentType
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
    <tr>
      <td>
        index
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>Promise</code> TODO




<div id="remove"></div>
<h2>
  <code>remove(index)</code>

</h2>

Removes a view from the nav stack at the specified index.



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        index
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>Promise</code> TODO




<div id="setViews"></div>
<h2>
  <code>setViews(components, opts)</code>

</h2>

Set the view stack to reflect the given component classes.



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        components
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
    <tr>
      <td>
        opts
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>Promise</code> TODO




<div id="setRoot"></div>
<h2>
  <code>setRoot(componentType, params, opts)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        componentType
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
    <tr>
      <td>
        params
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
    <tr>
      <td>
        opts
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>Promise</code> TODO




<div id="loadPage"></div>
<h2>
  <code>loadPage()</code>

</h2>












<div id="isSwipeBackEnabled"></div>
<h2>
  <code>isSwipeBackEnabled(val)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        val
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="canSwipeBack"></div>
<h2>
  <code>canSwipeBack()</code>

</h2>

If it's possible to use swipe back or not. If it's not possible
to go back, or swipe back is not enable then this will return false.
If it is possible to go back, and swipe back is enabled, then this
will return true.






* Returns: 
  <code>boolean</code> 




<div id="canGoBack"></div>
<h2>
  <code>canGoBack()</code>

</h2>

Returns `true` if there's a valid previous view that we can pop back to.
Otherwise returns false.






* Returns: 
  <code>boolean</code> 




<div id="navbarViewContainer"></div>
<h2>
  <code>navbarViewContainer(nbContainer)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        nbContainer
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="anchorElementRef"></div>
<h2>
  <code>anchorElementRef()</code>

</h2>

TODO






* Returns: 
  <code>TODO</code> TODO




<div id="getActive"></div>
<h2>
  <code>getActive()</code>

</h2>

TODO






* Returns: 
  <code>TODO</code> TODO




<div id="getByIndex"></div>
<h2>
  <code>getByIndex(index)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        index
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="getPrevious"></div>
<h2>
  <code>getPrevious(view)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        view
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="getStagedEnteringView"></div>
<h2>
  <code>getStagedEnteringView()</code>

</h2>

TODO






* Returns: 
  <code>TODO</code> TODO




<div id="getStagedLeavingView"></div>
<h2>
  <code>getStagedLeavingView()</code>

</h2>

TODO






* Returns: 
  <code>TODO</code> TODO




<div id="first"></div>
<h2>
  <code>first()</code>

</h2>

First view in this nav controller's stack. This would
not return an view which is about to be destroyed.






* Returns: 
  <code>TODO</code> TODO




<div id="last"></div>
<h2>
  <code>last()</code>

</h2>

Last view in this nav controller's stack. This would
not return an view which is about to be destroyed.






* Returns: 
  <code>TODO</code> TODO




<div id="indexOf"></div>
<h2>
  <code>indexOf(view)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        view
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="length"></div>
<h2>
  <code>length()</code>

</h2>

Number of sibling views in the nav controller. This does
not include views which are about to be destroyed.






* Returns: 
  <code>TODO</code> TODO




<div id="instances"></div>
<h2>
  <code>instances()</code>

</h2>

TODO






* Returns: 
  <code>TODO</code> TODO




<div id="isActive"></div>
<h2>
  <code>isActive(view)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        view
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="isStagedEntering"></div>
<h2>
  <code>isStagedEntering(view)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        view
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>






* Returns: 
  <code>TODO</code> TODO




<div id="registerRouter"></div>
<h2>
  <code>registerRouter(router)</code>

</h2>

TODO



<table class="table" style="margin:0;">
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    
    <tr>
      <td>
        router
        
        
      </td>
      <td>
        
  <code>TODO</code>
      </td>
      <td>
        <p>TODO</p>

        
      </td>
    </tr>
    
  </tbody>
</table>









