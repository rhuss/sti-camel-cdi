# Camel CDI QuickStart

This example shows how to work with Camel in the Java Container using CDI to configure components,
endpoints and beans.

This example is implemented using Java code with CDI injected resources.
The source code is provided in the following java file `src/main/java/io/fabric8/quickstarts/camelcdi/MyRoute.java`,
which can be viewed from [github](https://github.com/fabric8io/quickstarts/blob/master/quickstarts/java/camel-cdi/src/main/java/io/fabric8/quickstarts/camelcdi/MyRoute.java).

This example pickup incoming files, calls a Java bean `SomeBean` to transform the message, and writes the output to a file.


## STI

This example can be used with OpenShift's Source-To-Build technology.

To run it standalone use

```
s2i build . fabric8/sti-java-jboss-jdk8:1.0.6 fabric8/camel-cdi
```

To run it within os3

```
oc new-app --strategy=source fabric8/sti-java-jboss-jdk8:1.0.6~https://github.com/rhuss/sti-camel-cdi.git
```

or you can also use the provided `create-app.yml`:

```
oc create -f create-app.yml
```

In order to delete all objects associated with this app, do a 

```
oc delete all -l app=sti-camel-cdi
```
