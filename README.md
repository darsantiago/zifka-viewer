# Zifka Client Viewer

Static, serverless client-plan viewer for [Zifka Advisor](https://github.com/darsantiago/zifka-advisor).

The advisor generates a shareable URL of the form
`https://darsantiago.github.io/zifka-viewer/#<payload>` where `payload`
is a base64url-encoded JSON summary of the plan.

Everything after the `#` is a URL fragment — browsers do not send it to
GitHub, so **no client data ever reaches the server**. This page reads
the fragment and renders the plan. Integrity relies on the private
channel used by the advisor to share the URL (WhatsApp/email over HTTPS),
not on cryptographic signatures.
