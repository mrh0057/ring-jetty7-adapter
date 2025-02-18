# Jetty 7 adapter for Ring

## Synoptis

Adapter for Ring using Jetty 7.

Behaves exactly like the normal jetty adapter, but uses Jetty 7 instead of 6. 

For more information, consult the offical Ring site: http://mmcgrana.github.com/ring/

## Example:

"Hello World" in Ring:

    (use 'ring.adapter.jetty7)

    (defn app [req]
      {:status  200
       :headers {"Content-Type" "text/html"}
       :body    "Hello World from Ring and Jetty 7"})

    (run-jetty app {:port 8080})

## Download and Installation
Add the following dependency to your `project.clj` and do a `lein deps`.

    [org.signaut/ring-jetty7-adapter "0.3.11.4"]


## Adding Java Servlets

Servlet code taken from Maximilian Weber.

More information and examples: https://github.com/maxweber/hello-cometd

Adding a servlet to jetty example: 

       (let [servlets [{:url-pattern "/orders/*"
                        :servlet orders-servlet
                        :load-on-startup 1}]"]
          (run-jetty app {:port 8080 :servlets servlets}))
