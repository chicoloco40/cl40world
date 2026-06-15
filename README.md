# cl40world
App configuration file: shop.cl40.world
name = "Example App"
client_id = "a61950a2cbd5f32876b0b55587ec7a27"
application_url = "https://www.app.example.com/"
embedded = true
handle = "example-app"

[access_scopes]
scopes = "read_products"

[access.admin]
direct_api_mode = "online"

[auth]
redirect_urls = [
  "https://app.example.com/api/auth/callback",
  "https://app.example.com/api/auth/oauth/callback",
]

[customer_authentication]
redirect_uris = [
  "https://app.example.com/api/customer/auth/callback"
]
javascript_origins = [
  "https://app.example.com"
]
logout_urls = [
  "https://app.example.com/api/customer/logout"
]

[webhooks]
api_version = "2024-01"

[[webhooks.subscriptions]]
topics = [ "app/uninstalled" ]
compliance_topics = [ "customers/redact", "customers/data_request", "shop/redact" ]
uri = "/webhooks"

[events]
api_version = "unstable"

[[events.subscription]]
handle = "product-updates"
topic = "Product"
actions = ["create", "update", "delete"]
uri = "/events/products"

[app_proxy]
url = "https://app.example.com/api/proxy"
subpath = "store-pickup"
prefix = "apps"

[pos]
embedded = false

[app_preferences]
url = "https://www.app.example.com/preferences"

[build]
automatically_update_urls_on_dev = false
