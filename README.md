<img src="icon.png" alt="ActiveIQ" width="64" height="64">

# ActiveIQ Tracking Code for Google Tag Manager

This tag adds the ActiveIQ tracking code to your website through Google Tag Manager (GTM), so ActiveIQ can show you the companies and contacts visiting your site. You don't need to paste any code.

Setup takes about 5 minutes.

## Before you start

You need two things:

- **Your Workspace ID.** In ActiveIQ, click your name at the top right and choose **ActiveIQ Code**. Your Workspace ID is the number after `__pid=` in the code on that page. For example, in `__pid=12345;` the Workspace ID is `12345`. Not every user can open this page. If you don't see it, ask your ActiveIQ admin.
- **Publish access to your website's GTM container.**

## Install the tag

1. In Google Tag Manager, open your website's container and go to **Tags > New**.
2. Click **Tag Configuration**, then **Discover more tag types in the Community Template Gallery**.
3. Search for **ActiveIQ**, choose **ActiveIQ Tracking Code**, and click **Add to workspace**. Confirm when GTM asks.
4. In **Workspace ID**, enter your Workspace ID.
5. Click **Triggering** and choose **All Pages**.
6. Name the tag (for example "ActiveIQ") and click **Save**.
7. Click **Submit**, then **Publish**. The tag is live on your website once it's published.

## Check that it works

1. In GTM, click **Preview** and enter your website's address.
2. Your website opens in a new tab. In the Tag Assistant tab, **ActiveIQ Tracking Code** should be listed under **Tags Fired**.
3. Visit a few pages. They show up in ActiveIQ shortly after.

## Already have the ActiveIQ code on your site?

Keep only one copy. If you installed ActiveIQ before with a **Custom HTML** tag in GTM, or pasted the code into your website, remove that copy once this tag is published. Otherwise visits may be counted twice.

## Not receiving any data?

- **Check the trigger.** The tag should fire on **All Pages**. If it only fires on some pages, only those pages are tracked.
- **Check the Workspace ID.** A wrong number sends your visits to the wrong place without any error. Compare it with the number on the ActiveIQ Code page.
- **Check your website domain.** It must be listed in ActiveIQ under **Account Settings**.
- **Check the date range** in ActiveIQ. Try a wider range, such as the last 30 days.

Still stuck? Visit the [ActiveIQ Help Center](https://support.activeiq.co).

## What this tag does

When it fires, the tag:

- sets the global variable `__pid` to your Workspace ID;
- loads `https://live.activeiq.co/ac.js`, the ActiveIQ tracking script;
- then loads your workspace's settings script, `https://live.activeiq.co/pid/<Workspace ID>.js`;
- if the page had already finished loading by then (for example when a cookie consent banner releases the tag late), starts ActiveIQ tracking right away, since the tracking script normally starts when the page finishes loading.

This is what the ActiveIQ Code snippet does when it's pasted into a page. The template asks GTM for these permissions only: read and write the `__pid` global, read the `dataLayer` (to see whether the page has finished loading), start the tracking script (`__am_track`), load scripts from `live.activeiq.co`, and log to the browser console in Preview mode.

## License

Apache 2.0. See [LICENSE](LICENSE).
