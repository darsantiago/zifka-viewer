# Zifka Client Viewer

Static, serverless client-plan viewer for [Zifka Advisor](https://github.com/darsantiago/zifka-advisor).

The advisor generates a shareable URL of the form
`https://darsantiago.github.io/zifka-viewer/#<payload>.<sig>` where
`payload` is a base64url JSON summary and `sig` is a detached Ed25519
signature (same signing key as the rule-packs feed).

Everything after the `#` is a URL fragment — browsers do not send it to
GitHub, so **no client data ever reaches the server**. This page reads
the fragment, verifies the signature against the embedded public key,
and renders the plan.

If the signature fails, the page tells the reader to request a new link.
