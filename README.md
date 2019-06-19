# Honeywell Lyric Custom Component (for Home Assistant)

This will give support for the [Honeywell Lyric](http://yourhome.honeywell.com/en/products/thermostat/lyric-thermostat) thermostats in [Home Assistant](https://www.home-assistant.io/)

Visit [Honeywell Developers](http://developer.honeywell.com/), and sign in. Create an account if you don’t have one already.
Fill in account details.
Submit changes
Click “[My Apps](http://developer.honeywell.com/user/me/apps)” at top of page, under your account.
Click “[Create New App](http://developer.honeywell.com/user/me/apps/add)”
Fill in details:
App name. Can be anything, I use Home Assistant.
In the “Callback URL” enter the adress to your Home Assistant instance: “https://yourhomeassistant:8123/api/lyric/authenticate”. If you have base_url in your http config, use this url. Otherwise use your local ip.
Click “Save Changes”
On the apps page, click on the just created app.
The “Consumer Key” and “Consumer Secret” are shown now. These will be used as client_id and client_secret below.
Once Home Assistant is started, a configurator will pop up asking you to log into your Lyric account.

### Configuration
```yaml
# Example configuration.yaml entry
lyric:
  client_id: CLIENT_ID
  client_secret: CLIENT_SECRET
```

```yaml
# Example configuration.yaml entry to show only devices at your vacation and primary homes
lyric:
  client_id: CLIENT_ID
  client_secret: CLIENT_SECRET
  locations:
    - Vacation
    - Primary
```

Configuration variables:

- *client_id* (Required): Your Lyric developer client id.
- *client_secret* (Required): Your Lyric developer client secret.
- *locations* (Optional): The location or locations you would like to include devices from. If not specified, this will include all locations in your Lyric account.
