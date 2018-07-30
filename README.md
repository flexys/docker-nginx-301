# docker-nginx-301-redirect
Simple nginx container that 301 redirects all requests


Set $REDIRECT_TARGET in yr environment to base url to redirect to


This works best when configured via Helm as a k8s object.

Then you can have an ingress with multiple targets that all redirect to the 
same endpoint.

You will also discover that the second vhost that always returns 2xx is an
ideal target for a k8s liveness probe, rather than the primary vhost, because
k8s does not like redirects as an answer to that sort of thing. 
Yes, I know the doc alleges otherwise.
