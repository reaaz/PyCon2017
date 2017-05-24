# 5 ways to deploy your Python web app in 2017 by Andrew T. Baker
## `ngrok`
* Secure tunnels to localhost
* Pros
 * Fast and easy
 * Great for demos
 * Great for hacking on webhooks
* Cons
 * Stops when you close your laptop
 * Random domains (unless you pay)
 * Definitely doesn't scale (<12 people)
## Heroku
 * Pros
  * One app 24/7 for free
  * Zero server management
  * Add-ons ecosystem
 * Cons
  * Scaling is easy but gets pricey
  * Harder server customization
  * Some add-ons better than others
## "Serverless" (with AWS Lambda)
 * Zappa - third party library that makes it easier to deploy a Flask app to Lambda
 * API Gateway - used to set up custom domains, SSL
 * Bundles dependencies locally before deploying them to S3
 * Pros
  * Economical for small to medium loads
  * Good for "spikey" traffic
  * Zero server config
 * Cons
  * Relatively new technique
  * Less fun without Zappa
  * Can be tricky to troubleshoot
## Virtual Machines (Google Compute Engine)
 * Pros
  * Full control
  * Scales as much as your wallet
  * Economical if you're careful
 * Cons
  * More work for you
  * There's a lot more to learn
  * Harder to predict ultimate costs
## Docker
 * Pros
  * Helps with dev/prod parity
  * Nice for microservices
  * Impress your friends
 * Cons
  * Newer technique
  * Works best when you go all-in
  * Has its own learning curve
