Explain the concept of Hybrid Mobile App Development

Hybrid applications are web applications (or web pages) in the native browser, such as UIWebView in iOS and WebView in Android.
Hybrid apps are developed using HTML, CSS and Javascript, and then wrapped in a native application using platforms like Cordova.
This allows you to use any web-native framework you want, and there are plenty of these.

-------------------------------------------------------
Explain the Pros & Cons of using Hybrid Mobile App Development compared to Native App Development

Pros:
The application development is faster, simpler, more rapid and the application is easier to maintain.

You can change platforms anytime you need, Cordova lets you build your application for more than one platform just by one adding line of code.

It's just like developing a webpage. You create HTML, CSS and JavaScript local files.


Cons:
The main problem with hybrid apps is that they still depend on the native browser, which means they are not as fast as native apps.


-------------------------------------------------------
Explain about the "building blocks" involved in an ionic Hybrid Application
Ionic is a powerful HTML5 SDK that helps you build native-feeling mobile apps using web technologies like HTML, CSS, and Javascript.



-------------------------------------------------------
Explain and demonstrate ways to debug Hybrid Mobile Applications Running on a real device

With Chrome you can type chrome://inspect into your address bar As soon as you are running your Android app,
you can inspect the app when you are running it with the "ionic run android".


-------------------------------------------------------
Explain when and why CORS is a problem for Hybrid Mobile Applications

CORS = Cross origin resource sharing.

When you run ionic serve a local web server is started up.
Your browser is opened to point at the local server address.
Your origin will be localhost.
Any AJAX request sent out to a host other than localhost will have localhost as its origin and thus will require a CORS preflight request
to see if it can access the resource.


-------------------------------------------------------
Explain how and why it is possible for a Hybrid Application to access native phone devices like location,
calendar etc.

Current hybrid mobile applications are almost a marvel of modern web/mobile development.
Where it was impossible few year ago, now you can use JavaScript and access any smartphone hardware.
The rise of HTML5 has brought a surge of access to device hardware. Geolocation (GPS), the Orientation API (accelerometer),
WebGL (GPU), and the Web Audio API (audio hardware) are perfect examples.
These features are ridiculously powerful, exposing high level JavaScript APIs that sit on top of the system's underlying hardware capabilities.

ngCordova comes with over 70 native Cordova plugins that you can easily add to your Angular Cordova apps.

-------------------------------------------------------
Explain using an example how your Hybrid Application communicates with a backend and how CORS problems were solved (if any)

The easiest way to handle the CORS problem is to ultimately ask your API provider to allow all hosts. However, this isn’t always an option.

Using the Angular constant and the replace module will give us a happy medium, in which we can work around CORS:

angular.module('starter', ['ionic', 'starter.controllers', 'starter.services'])
.constant('ApiEndpoint', {
  url: 'http://localhost:8100/api'
})

angular.module('starter.services', [])

.factory('Api', function($http, ApiEndpoint) {
  console.log('ApiEndpoint', ApiEndpoint)

  var getApiData = function() {
    return $http.get(ApiEndpoint.url + '/tasks')
      .then(function(data) {
        console.log('Got some data: ', data);
        return data;
      });
  };

  return {
    getApiData: getApiData
  };
})


-------------------------------------------------------