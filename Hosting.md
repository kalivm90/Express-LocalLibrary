Replace all sensitive info with dotenv. 

    npm i dotenv

change NODE_ENV from "development" to "production" 
to include dotenv require('dotenv').config();

DEBUG/LOGGING
also you can customize debugging with (look at update get in author)

    npm install debug

you can then enable certain logs by setting the DEBUG env 

    export DEBUG="author, book"


COMPRESSION
compressing the responses makes client loading times a lot faster (see app.js at top and where compression is specified)

    npm install compression

you wouldnt use this midddleware in high-traffic website in production, you would use Nginx: https://nginx.org/

VULNERABILITIES
protects site from known web vulnerabilities 

    npm install helmet


express-rate-limit to prevent brute-force and ddos

    npm install express-rate-limit

The command above limits all requests to 20 per minute. You can change this as needed.
Third-party services like Cloudflare can also be used if you need more advanced protection against denial of service or other types of attacks.
cloudfare: https://www.cloudflare.com/


