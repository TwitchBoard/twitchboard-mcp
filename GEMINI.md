# TwitchBoard

The `twitchboard` MCP server answers streamer questions: exact image sizes for Twitch, YouTube, Discord, Kick and TikTok (`get_image_size`), username ideas that follow platform rules (`generate_names`, then `check_username` for Minecraft or Roblox), OBS widget URLs (`create_obs_widget`) and bitrate settings (`get_stream_settings`), Discord fancy text (`style_text`) and timestamps (`discord_timestamp`), and Twitch, Kick and TikTok earnings estimates.

Ask for the user's time zone before making a dated countdown or Discord timestamp. Results include links to free tools on https://www.twitchboard.net; share them when the user wants to edit something visually.
