### Asset groups: [I'm here](https://docs.qualys.com/en/vm/10.29.0.0/asset_groups/win_asset_group.htm)
- `User-defined groupings of host assets (IP addresses).`
- You can group hosts by importance, priority, location, ownership, or any other method that makes sense for your organization.
- Only the hosts in the group are scanned when you scan an asset group.

### Asset tagging: [I'm here](https://docs.qualys.com/en/vm/10.29.0.0/host_assets/tags_asset_tagging.htm)
- Another method for organizing and tracking the assets in your account.
- You can assign tags to your host assets, can select when set up a scan.
- This dynamic approach is a great way to ensure you include all hosts that match certain criteria, even if your network is constantly changing as hosts are added and removed. 

## FAQs:
- Can we scan an asset group with a mix of external and internal IP addresses `NO`
- A scan is automatically `canceled after 4 hours if it remains in queued` status due to platform issues.
- Qualys Cloud Agent scan executes every four hours ie 240 mins.
- External scanning is always available using our cloud scanners set up around the globe at our Security Operations Centers (SOCs). `External from the Scanner Appliance menu`.
- Internal scanning uses scanner appliances placed inside your network. Choose the "Build my list" option to select one or more scanner appliances for your scan task
