# Smart iFrame (Zendesk App)

Easily embed a 3rd party application or website into your Zendesk agent workspace just by specifying the URL.

Get it now in the Zendesk App Marketplace: https://www.zendesk.com/marketplace/apps/support/1020069/smart-iframe/

You can leverage data about the Zendesk ticket, assigned user, current user, and requester to formulate dynamic URLs

Available template strings:

- `{ticket_id}`
- `{current_user_id}`
- `{current_user_email}`
- `{requester_id}`
- `{requester_email}`
- `{requester_external_id}`
- `{assignee_id}`
- `{assignee_email}`

For example, setting up the app with URL `https://mysite.com/profile/{requester_id}` will result in an embedded iFrame to URL `https://mysite.com/profile/1234` where `1234` is the Zendesk user ID of the ticket requester (aka customer)

![screenshot-1](https://github.com/user-attachments/assets/58117894-59c4-4c47-b75a-2749b9fcb751)
![screenshot-2](https://github.com/user-attachments/assets/7d13a447-dced-442a-aeef-6a80c03b35b8)


### iFrame Not Working?

Not all websites can be rendered within an iFrame. If you see this:

![screenshot-3](https://github.com/user-attachments/assets/9c530d40-8e86-491e-aa09-084d9c4ee1c2)

The application may be blocking this behavior. This is a decision made by the respective website owner / administrator.

Opening the browser developer tools console should present some additional information, such as:

```
Refused to display 'https://thewebsiteyouwanttoiframe.com/' in a frame because it set 'X-Frame-Options' to 'sameorigin'.
```

If you are attempting to configure Smart iFrame with a 3rd party vendor application, you can reach out to their support department and discuss further.

If you or your company owns the website you are trying to iFrame, you may need to speak with your system administrator about disabling restrictive controls that are set via the HTTP header `X-Frame-Options`

If `X-Frame-Options` is set to `DENY` or `SAMEORIGIN` (and it doesn't match the criteria), the browser will block the framing.
