BE( 1.Base —> 2.DB) —> 3.FEx2 —> 4.Tests —> 5.FE+x2 —> 6.Packaging

1. Setup basic html app (URLconf, views)
2. Setup sys tables, app models
3. Admin page, views (templates, non-hard urls, namespacing)
4. *skip*
5. Static, styles
6. *skip*

Deploy.
nic.ru, cloudflare.com
1. Buy domain name
2. Acquire DNS host (may be on the same service where you bought domain name)
3. Delegate new DNS for acquired domain
4. Setup port forwarding on router (so router transmits all the trafic to the server)
(Local ports — Apache setup's port; External ports — 80//http, 443//https)
https://developers.cloudflare.com/fundamentals/get-started/reference/network-ports/

+. Add Security features. Block unwanted regions within DNS service

//Local IP points on the router — not the machine itself. Port does.