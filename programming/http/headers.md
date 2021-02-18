# Headers

## Content-Security-Policy

https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP

Allows restrictions to be placed on where content can be downloaded and executed from. For example,
if a strict Content-Security-Policy is in place, then a XSS attack couldn't inject a script
into the page and run it, because `unsafe-inline` is not permitted.

# Referrer-Policy

https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy

Allows restrictions to be placed on when the Referer (sic) will
be passed along.

# X-Content-Type-Options

https://www.chromium.org/Home/chromium-security/corb-for-developers

Adding `nosniff` as the value to this prevents some browsers from
attempting to reinterpret values of these. For example, a
`<script>` pointing at a .json file to be used as part of an attack.