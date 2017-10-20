# ms-location

A node module to auto register and discover microservices

How to use it?

- Install
````
npm install git://github.com/shri1920/ms-location.git
````

- Usage
````
var MsLocation = require("ms-location"),
    msLocation = new MsLocation("127.0.0.1", "2379", "services");
````

- To register info for myservice_1
````
var info = {
    host     : "127.0.0.1",
    port     : 3000,
	protocol : "http",
	api      : "/service/v1"
};
msLocation.register("myservice_1", info).then(function (data) {
    console.log(data);
}).catch(function (err) {
    console.log(err);
});
````

- To get the details of myservice_1
````
msLocation.discover("myservice_1").then(function (data) {
    console.log(data);
}).catch(function (err) {
    console.log(err);
});
````

- To remove the info for myservice_1 from registry
````
msLocation.remove("myservice_1").then(function (data) {
    console.log(data);
}).catch(function (err) {
    console.log(err);
});
````

