<font size=6 style="margin: auto"> <center>
[Market docs](https://github.com/AS7RIDENIED/LOLZTEAM/blob/main/LOLZTEAM/Documentation/Market.md) - [Antipublic Docs](https://github.com/AS7RIDENIED/LOLZTEAM/blob/main/LOLZTEAM/Documentation/Antipublic.md)
[Utility docs](https://github.com/AS7RIDENIED/LOLZTEAM/blob/main/LOLZTEAM/Documentation/Utils.md)
</center></font>

<details>

<summary><font size="4">Method tree</font></summary>

* [Threads](#threads)
  * [Contests](#contests)
    * [Create upgrade contest (time)](#create-upgrade-contest-time)
    * [Create upgrade contest (count)](#create-upgrade-contest-count)
    * [Create money contest (time)](#create-money-contest-time)
    * [Create money contest (count)](#create-money-contest-count)
  * [Arbitrage](#arbitrage)
    * [Market](#market)
    * [Non Market](#non-market)
  * [Get threads](#get-threads)
  * [Create thread](#create-thread)
  * [Edit thread](#edit-thread)
  * [Get thread](#get-thread)
  * [Delete thread](#delete-thread)
  * [Get thread followers](#get-thread-followers)
  * [Get followed threads](#get-followed-threads)
  * [Follow thread](#follow-thread)
  * [Unfollow thread](#unfollow-thread)
  * [Get thread navigation](#get-thread-navigation)
  * [Get thread votes](#get-thread-votes)
  * [Thread vote](#thread-vote)
  * [Get new threads](#get-new-threads)
  * [Get recent threads](#get-recent-threads)
  * [Bump thread](#bump-thread)
* [Posts](#posts)
  * [Post comments](#post-comments)
    * [Get post comment](#get-post-comment)
    * [Create post comment](#create-post-comment)
  * [Get posts](#get-posts)
  * [Get post](#get-post)
  * [Create post](#create-post)
  * [Edit post](#edit-post)
  * [Delete post](#delete-post)
  * [Get post likes](#get-post-likes)
  * [Like post](#like-post)
  * [Unlike post](#unlike-post)
  * [Report post](#report-post)
* [Forums](#forums)
  * [Get forums](#get-forums)
  * [Get forum](#get-forum)
  * [Get forum followers](#get-forum-followers)
  * [Get followed forums](#get-followed-forums)
  * [Follow forum](#follow-forum)
  * [Unfollow forum](#unfollow-forum)
* [Users](#users)
  * [Avatar](#avatar)
    * [Upload avatar](#upload-avatar)
    * [Delete avatar](#delete-avatar)
    * [Crop avatar](#crop-avatar)
  * [Get users](#get-users)
  * [Get user](#get-user)
  * [Edit user](#edit-user)
  * [Get user fields](#get-user-fields)
  * [Search users](#search-users)
  * [Lost password](#lost-password)
  * [Get user followings](#get-user-followings)
  * [Get user followers](#get-user-followers)
  * [Follow user](#follow-user)
  * [Unfollow user](#unfollow-user)
  * [Get ignored users](#get-ignored-users)
  * [Ignore user](#ignore-user)
  * [Unignore user](#unignore-user)
  * [Get user groups](#get-user-groups)
* [Profile posts](#profile-posts)
  * [Profile post comments](#profile-post-comments)
    * [Get profile post comments](#get-profile-post-comments)
    * [Get profile post comment](#get-profile-post-comment)
    * [Create profile post comment](#create-profile-post-comment)
    * [Delete profile post comment](#delete-profile-post-comment)
  * [Get profile posts](#get-profile-posts)
  * [Get profile post](#get-profile-post)
  * [Create profile post](#create-profile-post)
  * [Edit profile post](#edit-profile-post)
  * [Delete profile post](#delete-profile-post)
  * [Get profile post likes](#get-profile-post-likes)
  * [Like profile post](#like-profile-post)
  * [Unlike profile post](#unlike-profile-post)
  * [Report profile post](#report-profile-post)
* [Conversations](#conversations)
  * [Conversation messages](#conversation-messages)
    * [Get conversation messages](#get-conversation-messages)
    * [Get conversation message](#get-conversation-message)
    * [Send conversation message](#send-conversation-message)
    * [Edit conversation message](#edit-conversation-message)
    * [Delete conversation message](#delete-conversation-message)
    * [Report conversation message](#report-conversation-message)
  * [Get conversations](#get-conversations)
  * [Get conversation](#get-conversation)
  * [Create conversation](#create-conversation)
  * [Create group conversation](#create-group-conversation)
  * [Leave from conversation](#leave-from-conversation)
* [Notifications](#notifications)
  * [Get notifications](#get-notifications)
  * [Get notification](#get-notification)
  * [Read notification/s](#read-notifications)
  * [Send custom notification](#send-custom-notificaton)
* [Categories](#categories)
  * [Get categories](#get-categories)
  * [Get category](#get-category)
* [Pages](#pages)
  * [Get pages](#get-pages)
  * [Get page](#get-page)
* [Tags](#tags)
  * [Get popular tags](#get-popular-tags)
  * [Get tags](#get-tags)
  * [Tagged contents](#tagged-contents)
  * [Find tags](#find-tags)
* [Search](#search)
  * [Search for threads](#search-for-threads)
  * [Search for posts](#search-for-posts)
  * [Search for all types of content](#search-for-all-types-of-content)
  * [Search for tagged](#search-for-tagged)
  * [Search indexing](#search-indexing)
* [Oauth](#oauth)
  * [Facebook oauth](#facebook-oauth)
  * [Twitter oauth](#twitter-oauth)
  * [Google oauth](#google-oauth)
  * [Associate oauth](#associate-oauth)
  * [Admin oauth](#admin-oauth)
* [Navigation](#navigation)
* [Get batch job](#get-batch-job)
* [Batch](#batch)
* [Send async](#send-async)

</details>

# Quickstart

You need to create class instance to use library

```
from LOLZTEAM import AutoUpdate
from LOLZTEAM import Constants
from LOLZTEAM.API import Forum, Market
from LOLZTEAM.Tweaks import DelaySync, SendAsAsync, CreateJob

token = "your_token"

market = Market(token=token, language="en")
forum = Forum(token=token, language="en")
```

**Parameters:**

- **token** (str): Your token.
  > You can get in there -> https://zelenka.guru/account/api
- **bypass_429** (bool): Bypass status code 429 by sleep
  > It's True by default. You can skip it or set False if you want
- **language** (str): Language for your api responses. 
  > Pass "en" if you want to get responses in english or pass "ru" if you want to get responses in russian.
- **proxy_type** (str): Your proxy type. 
  > You can use types ( Constants.Proxy.socks5 or socks4,https,http )
- **proxy** (str): Proxy string. 
  > Example -> ip:port or login:password@ip:port

# Threads

*Methods for getting, creating threads*

---

## Contests

*Methods for creating contests*

### Create upgrade contest (time)

*Create upgrade contest by time.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadscreate)*

**Parameters:**

- **post_body** (str): Content of the new thread.
- **prize_data_upgrade** (int): Which upgrade will each winner receive.
- **count_winners** (int): Winner count (prize count). 
  > The maximum value is 100.
- **length_value** (int): Giveaway duration value. 
  > The maximum duration is 3 days.
- **length_option** (str): Giveaway duration type. Can be [minutes, hours, days]. 
  > The maximum duration is 3 days.
- **require_like_count** (int): Sympathies for this week.
- **require_total_like_count** (int): Symapthies for all time.
- **secret_answer** (str): Secret answer of your account.
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **title** (str): Thread title. Can be skipped if title_en set.
- **title_en** (str): Thread title in english. Can be skipped if title set.
- **prefix_ids** (list): Thread prefixes.
- **tags** (list): Thread tags.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers

**Example:**

```python
response = forum.threads.contests.upgrade.create_by_time(title="Api example", post_body="Api example",
                                                         prize_data_upgrade=Constants.Forum.Contests.UpgradePrize.uniq,
                                                         count_winners=1, length_value=3,
                                                         length_option=Constants.Forum.Contests.Length.days,
                                                         require_like_count=1, require_total_like_count=1,
                                                         secret_answer="Secret answer")
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create upgrade contest (count)

*Create upgrade contest by members count.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadscreate)*

**Parameters:**

- **post_body** (str): Content of the new thread.
- **prize_data_upgrade** (int): Which upgrade will each winner receive.
- **count_winners** (int): Winner count (prize count). 
  > The maximum value is 100.
- **needed_members** (int): Max member count.
- **require_like_count** (int): Sympathies for this week.
- **require_total_like_count** (int): Symapthies for all time.
- **secret_answer** (str): Secret answer of your account.
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **title** (str): Thread title. Can be skipped if title_en set.
- **title_en** (str): Thread title in english. Can be skipped if title set.
- **prefix_ids** (list): Thread prefixes.
- **tags** (list): Thread tags.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers

**Example:**

```python
response = forum.threads.contests.upgrade.create_by_count(title="Api example", post_body="Api example",
                                                          prize_data_upgrade=Constants.Forum.Contests.UpgradePrize.uniq,
                                                          count_winners=1, needed_members=300, require_like_count=1,
                                                          require_total_like_count=1, secret_answer="Secret answer")
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create money contest (time)

*Create money contest by time.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadscreate)*

**Parameters:**

- **post_body** (str): Content of the new thread.
- **prize_data_money** (int): How much money will each winner receive.
- **count_winners** (int): Winner count (prize count).
  > The maximum value is 100.
- **length_value** (int): Giveaway duration value. 
  > The maximum duration is 3 days.
- **length_option** (str): Giveaway duration type. 
  > Can be [minutes, hours, days]. The maximum duration is 3 days.
- **require_like_count** (int): Sympathies for this week.
- **require_total_like_count** (int): Symapthies for all time.
- **secret_answer** (str): Secret answer of your account.
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **title** (str): Thread title. Can be skipped if title_en set.
- **title_en** (str): Thread title in english. Can be skipped if title set.
- **prefix_ids** (list): Thread prefixes.
- **tags** (list): Thread tags.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers

**Example:**

```python
response = forum.threads.contests.money.create_by_time(title="Api example", post_body="Api example",
                                                       prize_data_money=500,
                                                       count_winners=1, length_value=3,
                                                       length_option=Constants.Forum.Contests.Length.days,
                                                       require_like_count=1, require_total_like_count=1,
                                                       secret_answer="Secret answer")
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create money contest (count)

*Create money contest by members count.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadscreate)*

**Parameters:**

- **post_body** (str): Content of the new thread.
- **prize_data_money** (int): How much money will each winner receive.
- **count_winners** (int): Winner count (prize count).
  > The maximum value is 100.
- **needed_members** (int): Max member count.
- **require_like_count** (int): Sympathies for this week.
- **require_total_like_count** (int): Symapthies for all time.
- **secret_answer** (str): Secret answer of your account.
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **title** (str): Thread title. Can be skipped if title_en set.
- **title_en** (str): Thread title in english. Can be skipped if title set.
- **prefix_ids** (list): Thread prefixes.
- **tags** (list): Thread tags.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers

**Example:**

```python
response = forum.threads.contests.money.create_by_count(title="Api example", post_body="Api example",
                                                        prize_data_money=500,
                                                        count_winners=1, needed_members=300, require_like_count=1,
                                                        require_total_like_count=1, secret_answer="Secret answer")
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

---

## Arbitrage

---

### Market

*Create a Arbitrage.*

**Parameters:**

- **responder** (str): To whom the complaint is filed. Specify a nickname or a link to the profile.
- **item_id** (int or str): Write account link or item_id.
- **amount** (float): Amount by which the responder deceived you.
- **post_body** (str): You should describe what's happened.
- **currency** (str): Currency of Arbitrage.
- **conversation_screenshot** (str): Screenshot showing the respondent's Telegram login. If the correspondence was conducted in Telegram, upload screenshot that will display the respondent's Telegram login against the background of your dialogue. The screenshot must be uploaded to Imgur. If the correspondence was conducted elsewhere, write "no".
- **tags** (list): Thread tags.
- **hide_contacts** (bool): Hide contacts.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers
- **reply_group** (int): Allow to reply only users with chosen or higher group.

**Example:**

```python
response = forum.threads.arbitrage.market(
    responder="AS7RID",
    item_id=2410024,
    amount=500,
    post_body="Wrong account password. Give my money back",
    conversation_screenshot="no",
    currency="rub",
)
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Non Market

*Create a Arbitrage.*

**Parameters:**

- **responder** (str): To whom the complaint is filed. Specify a nickname or a link to the profile.
- **amount** (float): Amount by which the responder deceived you.
- **receipt** (str): Funds transfer recipient. Upload a receipt for the transfer of funds, use the "View receipt" button in your wallet. Must be uploaded to Imgur. Write "no" if you have not paid.
- **post_body** (str): You should describe what's happened.
- **pay_claim** (bool): !!!  If you set this parameter to **True** forum will automatically calculate the amount and debit it from your account.  !!!   
- **conversation_screenshot** (str): Screenshot showing the respondent's Telegram login. If the correspondence was conducted in Telegram, upload screenshot that will display the respondent's Telegram login against the background of your dialogue. The screenshot must be uploaded to Imgur. If the correspondence was conducted elsewhere, write "no".
- **responder_data** (str): Contacts and wallets of the responder. Specify the known data about the responder (Skype, Vkontakte, Qiwi, WebMoney, etc.), if any.
- **currency** (str): Currency of Arbitrage.
- **transfer_type** (str): The transaction took place through a guarantor or there was a transfer to the market with a hold? Can be ["safe", "notsafe"] 
- **tags** (list): Thread tags.
- **hide_contacts** (bool): Hide contacts.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **** (any):

**Example:**

```python
response = forum.threads.arbitrage.non_market(
    responder="AS7RID",
    amount=500,
    currency="rub",
    receipt="*screenshot*",
    post_body="I got scammed. I buyed something but responder didn't give it to me. Check attached screenshots",
    pay_claim=False,
    conversation_screenshot="*screenshot*",
)
print(response)
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

---

### Get threads

*List of threads in a forum (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetthreads)*

**Parameters:**

- **forum_id** (int): ID of the containing forum. Can be skipped if thread_ids set.
- **thread_ids** (str): ID's of needed threads (separated by comma).
  > If this parameter is set, all other filtering parameters will be ignored.
- **creator_user_id** (int): Filter to get only threads created by the specified user.
- **sticky** (bool): Filter to get only sticky <sticky=1> or non-sticky <sticky=0> threads. 
  > By default, all threads will be included and sticky ones will be at the top of the result on the first page. In mixed mode, sticky threads are not counted towards threads_total and does not affect pagination.
- **thread_prefix_id** (int): Filter to get only threads with the specified prefix.
- **thread_tag_id** (int): Filter to get only threads with the specified tag.
- **page** (int): Page number of threads.
- **limit** (int): Number of threads in a page.
- **order** (str): Threads sorting order.
  > Can be [natural, thread_create_date, thread_create_date_reverse, thread_update_date, thread_update_date_reverse, thread_view_count, thread_view_count_reverse, thread_post_count, thread_post_count_reverse]

**Example:**

```python
response = forum.threads.get_threads(forum_id=876)
print(response.json())
```

```python
{'threads': [{'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create thread

*Create a new thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadscreate)*

**Parameters:**

- **forum_id** (int): ID of the target forum.
- **post_body** (str): Content of the new thread.
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **title** (str): Thread title. Can be skipped if title_en set.
- **title_en** (str): Thread title in english. Can be skipped if title set.
- **prefix_ids** (list): Thread prefixes.
- **tags** (list): Thread tags.
- **hide_contacts** (bool): Hide contacts.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.
- **dont_alert_followers** (bool): Don't alert followers.
- **kwargs** (any): Any another params

**Example:**

```python
response = forum.threads.create(forum_id=876, title="Api example", post_body="Api example", )
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Edit thread

*Edit a thread.*

**Parameters:**

- **thread_id** (int): Id of thread.
- **title** (str): Thread title.
- **title_en** (str): Thread title in english.
- **prefix_ids** (list): Thread prefixes.
- **tags** (list): Thread tags.
- **discussion_open** (bool): Discussion state.
- **hide_contacts** (bool): Hide contacts.
- **allow_ask_hidden_content** (bool): Allow ask hidden content.
- **reply_group** (int): Allow to reply only users with chosen or higher group.
- **comment_ignore_group** (bool): Allow commenting if user can't post in thread.

**Example:**

```python
response = forum.threads.edit(
    thread_id=5974102,
    title="Edited title",
    discussion_open=False,
    reply_group=Constants.Forum.ReplyGroups.staff,
)
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Move thread

*Move a thread.*

**Parameters:**

- **thread_id** (int): Id of thread.
- **forum_id** (int): Target forum id.
- **title** (str): Thread title.
- **title_en** (str): Thread title in english.
- **prefix_ids** (list): Thread prefixes.
- **send_alert** (bool): Send a notification to users who are followed to target node.
- **send_starter_alert** (bool): Send alert to thread starter.
- **starter_alert_reason** (str): Reason of moving thread which will sent to thread starter. (Required if **send_starter_alert** is set)

**Example:**

```python
response = forum.threads.move(thread_id=6301330, forum_id=976)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get thread

*Detail information of a thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetthread)*

**Parameters:**

- **thread_id** (int): ID of thread.

**Example:**

```python
response = forum.threads.get(thread_id=5523020)
print(response.json())
```

```python
{'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Delete thread

*Delete a thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsdelete)*

**Parameters:**

- **thread_id** (int): ID of thread.
- **reason** (str): Reason of the thread removal.

**Example:**

```python
response = forum.threads.delete(thread_id=5523020, reason="No reason :c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get thread followers

*List of a thread's followers. For privacy reason, only the current user will be included in the list.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetfollowthread)*

**Parameters:**

- **thread_id** (int): ID of thread.

**Example:**

```python
response = forum.threads.followers(thread_id=5523020)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string', 'follow': {'alert': True, 'email': True}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get followed threads

*List of followed threads by current user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetfollowedthreads)*

**Parameters:**

- **total** (bool): If included in the request, only the thread count is returned as threads_total.

**Example:**

```python
response = forum.threads.followed()
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Follow thread

*Follow a thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsfollowthread)*

**Parameters:**

- **thread_id** (int): ID of thread.
- **email** (bool): Whether to receive notification as email.

**Example:**

```python
response = forum.threads.follow(thread_id=5523020)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Unfollow thread

*Unfollow a thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsunfollowthread)*

**Parameters:**

- **thread_id** (int): ID of thread.

**Example:**

```python
response = forum.threads.unfollow(thread_id=5523020)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get thread navigation

*List of navigation elements to reach the specified thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetnavigationelements)*

**Parameters:**

- **thread_id** (int): ID of thread.

**Example:**

```python
response = forum.threads.navigation(thread_id=5523020)
print(response.json())
```

```python
{'elements': [{'category_id': 0, 'category_title': 'string', 'category_description': 'string', 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'sub-elements': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'navigation_type': 'string', 'navigation_id': 0, 'navigation_depth': 0, 'navigation_parent_id': 0, 'has_sub_elements': True, 'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'forum_is_followed': True}], 'elements_count': 0, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get thread votes

*Detail information of a poll.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetpoll)*

**Parameters:**

- **thread_id** (int): ID of thread.

**Example:**

```python
response = forum.threads.votes(thread_id=5523020)
print(response.json())
```

```python
{'poll_id': 0, 'poll_question': 'string', 'poll_vote_count': 0, 'poll_is_open': True, 'poll_is_voted': True, 'poll_max_votes': 0, 'responses': [{'response_id': 0, 'response_answer': 'string', 'response_is_voted': True, 'response_vote_count': 0, 'voters': [{'user_id': 0, 'username': 'string'}]}], 'permissions': {'vote': True, 'result': True}, 'links': {'votes': 'string'}}
```

### Thread vote

*Vote on a thread poll.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsvotepoll)*

**Parameters:**

- **thread_id** (int): ID of thread.
- **response_id** (int): The id of the response to vote for. 
  > Can be skipped if response_ids set.
- **response_ids** (list[int]): An array of ids of responses (if the poll allows multiple choices).

**Example:**

```python
response = forum.threads.vote(thread_id=5523020, response_id=264758)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get new threads

*List of unread threads (must be logged in).*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetunreadthreads)*

**Parameters:**

- **forum_id** (int): ID of the container forum to search for threads.
  > Child forums of the specified forum will be included in the search.
- **limit** (int): Maximum number of result threads. 
  > The limit may get decreased if the value is too large (depending on the system configuration).
- **data_limit** (int): Number of thread data to be returned. 
  > Default value is 20.

**Example:**

```python
response = forum.threads.new()
print(response.json())
```

```python
{'threads': [{'thread_id': 0}], 'data': [{'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get recent threads

*List of recent threads.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsgetrecentthreads)*

**Parameters:**

- **days** (int): Maximum number of days to search for threads.
- **forum_id** (int): ID of the container forum to search for threads. 
  > Child forums of the specified forum will be included in the search.
- **limit** (int): Maximum number of result threads. 
  > The limit may get decreased if the value is too large (depending on the system configuration).
- **data_limit** (int): Number of thread data to be returned. 
  > Default value is 20.

**Example:**

```python
response = forum.threads.recent()
print(response.json())
```

```python
{'threads': [{'thread_id': 0}], 'data': [{'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Bump thread

*Bump a thread.*

*[Official documentation reference](https://lolzteam.readme.io/reference/threadsbumpthread)*

**Parameters:**

- **thread_id** (int): ID of thread.

**Example:**

```python
response = forum.threads.bump(thread_id=5523020)
print(response.json())
```

```python
{'status': 'ok', 'message': 'string', 'system_info': {'visitor_id': 0, 'time': 0}}
```

# Posts

*Methods for getting and creating posts*

---

## Post comments

*Methods for getting and creating post comments*

### Get post comments

*List of post comments in a thread (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/postcommentsget)*

**Parameters:**

- **post_id** (int): ID of post.
- **before** (int): The time in milliseconds (e.g. 1652177794083) before last comment date

**Example:**

```python
response = forum.posts.comments.get(post_id=39769208)
print(response.json())
```

```python
{'comments': {'111': {'post_comment_id': 0, 'post_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_comment_body': 'string', 'post_comment_body_html': 'string', 'post_comment_body_plain_text': 'string', 'post_comment_like_count': 0, 'user_is_ignored': True, 'post_comment_is_published': True, 'post_comment_is_deleted': True, 'post_comment_update_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'post': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True}}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create post comment

*Create a new post comment.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postcommentscreate)*

**Parameters:**

- **post_id** (int): ID of post.
- **comment_body** (str): Content of the new post

**Example:**

```python
response = forum.posts.comments.create(post_id=39769208, comment_body="Api example")
print(response.json())
```

```python
{'comment': {'post_comment_id': 0, 'post_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_comment_body': 'string', 'post_comment_body_html': 'string', 'post_comment_body_plain_text': 'string', 'post_comment_like_count': 0, 'user_is_ignored': True, 'post_comment_is_published': True, 'post_comment_is_deleted': True, 'post_comment_update_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'post': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

---

### Get posts

*List of posts in a thread (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsgetposts)*

**Parameters:**

- **thread_id** (int): ID of the containing thread.
- **page_of_post_id** (int): ID of a post, posts that are in the same page with the specified post will be returned. 
  > thread_id may be skipped.
- **post_ids** (list): ID's of needed posts. 
  > If this parameter is set, all other filtering parameters will be ignored.
- **page** (int): Page number of posts.
- **limit** (int): Number of posts in a page.
  > Default value depends on the system configuration.
- **order** (int): Ordering of posts.
  > Can be [natural, natural_reverse, post_create_date, post_create_date_reverse].

**Example:**

```python
response = forum.posts.get_posts(thread_id=5523020)
print(response.json())
```

```python
{'posts': [{'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}], 'posts_total': 0, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get post

*Detail information of a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsgetpost)*

**Parameters:**

- **post_id** (int): ID of post.

**Example:**

```python
response = forum.posts.get(post_id=39769208)
print(response.json())
```

```python
{'post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create post

*Create a new post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postscreate)*

**Parameters:**

- **post_body** (str): Content of the new post.
- **thread_id** (int): ID of the target thread.
- **quote_post_id** (int): ID of the quote post. 
  > It's possible to skip thread_id if this parameter is provided. An extra check is performed if both parameters exist and does not match.

**Example:**

```python
response = forum.posts.create(thread_id=5523020, post_body="Good library, awesome author")
print(response.json())
```

```python
{'post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Edit post

*Edit a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsedit)*

**Parameters:**

- **post_id** (int): ID of post.
- **thread_title** (str): New title of the thread (only used if the post is the first post in the thread and the authenticated user can edit thread).
- **thread_prefix_id** (int): New id of the thread's prefix (only used if the post is the first post in the thread and the authenticated user can edit thread).
- **thread_tags** (str): New tags of the thread (only used if the post is the first post in the thread and the authenticated user can edit thread tags).
- **thread_node_id** (int): Move thread to new forum if the post is first post and the authenticated user can move thread.
- **post_body** (str): New content of the post.

**Example:**

```python
response = forum.posts.edit(post_id=39769208,thread_title="Библиотека для упрощения работы с API | LOLZTEAM Forum/Market/Antipublic Python")
print(response.json())
```

```python
{'post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Delete post

*Delete a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsdelete)*

**Parameters:**

- **post_id** (int): ID of post.
- **reason** (str): Reason of the post removal.

**Example:**

```python
response = forum.posts.delete(post_id=39769208, reason="No reason :c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get post likes

*List of users who liked a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsgetliked)*

**Parameters:**

- **post_id** (int): ID of post.
- **page** (int): Page number of users.
- **limit** (int): Number of users in a page. 
  > Default value depends on the system configuration.

**Example:**

```python
response = forum.posts.likes(post_id=39769208, limit=10, page=2)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string'}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Like post

*Like a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postslike)*

**Parameters:**

- **post_id** (int): ID of post.

**Example:**

```python
response = forum.posts.like(post_id=39769208)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Unlike post

*Unlike a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsunlike)*

**Parameters:**

- **post_id** (int): ID of post.

**Example:**

```python
response = forum.posts.unlike(post_id=39769208)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Report post

*Report a post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/postsreport)*

**Parameters:**

- **post_id** (int): ID of post.
- **message** (str): Reason of the report.

**Example:**

```python
response = forum.posts.report(post_id=39769208, message="No report message :c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

# Forums

*Methods for getting information about forums*

### Get forums

*List of all forums in the system.*

*[Official documentation reference](https://lolzteam.readme.io/reference/forumsgetforums)*

**Parameters:**

- **parent_category_id** (int): ID of parent category.
- **parent_forum_id** (int): ID of parent forum.
- **order** (str): Ordering of categories. 
  > Can be [natural, list]

**Example:**

```python
response = forum.forums.get_forums()
print(response.json())
```

```python
{'forums': [{'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}], 'forums_total': 0, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get forum

*Detail information of a forum.*

*[Official documentation reference](https://lolzteam.readme.io/reference/forumsgetforum)*

**Parameters:**

- **forum_id** (int): ID of forum.    

**Example:**

```python
response = forum.forums.get_forum(forum_id=969)
print(response.json())
```

```python
{'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get forum followers

*List of a forum's followers. For privacy reason, only the current user will be included in the list (if the user follows the specified forum).*

*[Official documentation reference](https://lolzteam.readme.io/reference/forumsgetfollowers)*

**Parameters:**

- **forum_id** (int): ID of forum.    

**Example:**

```python
response = forum.forums.followers(forum_id=969)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string', 'follow': {'post': True, 'alert': True, 'email': True}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get followed forums

*List of followed forums by current user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/forumsgetfollowed)*

**Parameters:**

- **total** (bool): If included in the request, only the forum count is returned as forums_total.

**Example:**

```python
response = forum.forums.followed(total=True)
print(response.json())
```

```python
{'forums': [{'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True, 'follow': {'post': True, 'alert': True, 'email': True}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Follow forum

*Follow a forum.*

*[Official documentation reference](https://lolzteam.readme.io/reference/forumssetfollow)*

**Parameters:**

- **forum_id** (int): ID of forum we want to get
- **prefix_ids** (list[int]): List of prefix id's.
- **minimal_contest_amount** (int): Minimal contest amount. (For forum_id=766)
- **post** (bool): Whether to receive notification for post.
- **alert** (bool): Whether to receive notification as alert.
- **email** (bool): Whether to receive notification as email.

**Example:**

```python
response = forum.forums.follow(forum_id=969, post=True, alert=True)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Изменения сохранены', 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Unfollow forum

*Unfollow a forum.*

*[Official documentation reference](https://lolzteam.readme.io/reference/forumssetunfollow)*

**Parameters:**

- **forum_id** (int): ID of forum.

**Example:**

```python
response = forum.forums.unfollow(forum_id=969)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Изменения сохранены', 'system_info': {'visitor_id': 0, 'time': 0}}
```

# Users

---

## Avatar

### Upload avatar

*Upload avatar for a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersuploadavatar)*

**Parameters:**

- **avatar** (bytes): Binary data of the avatar.
- **user_id** (int): ID of user. If you do not specify the user_id, then you will change the avatar of the current user

**Example:**

```python
with open("avatar.png", 'rb') as f:
    avatar = f.read()
response = forum.users.avatar.upload(user_id=2410024, avatar=avatar)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Upload completed successfully'}
```

### Delete avatar

*Delete avatar for a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersdeleteavatar)*

**Parameters:**

- **user_id** (int): ID of user. If you do not specify the user_id, then you will delete the avatar of the current user

**Example:**

```python
response = forum.users.avatar.delete(user_id=2410024)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Crop avatar

*Crop avatar for a user.*

**Parameters:**

- **user_id** (int): ID of user.
- **size** (int): Selection size. Minimum value - 16.
- **x** (int): The starting point of the selection by width.
- **y** (int): The starting point of the selection by height

**Example:**

```python
response = forum.users.avatar.crop(user_id=2410024,size=2000)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Upload completed successfully', 'system_info': {'visitor_id': 0, 'time': 0}}
```

---

### Get users

*List of users (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetall)*

**Parameters:**

- **page** (int): Page number of users.
- **limit** (int): Number of users in a page.

**Example:**

```python
response = forum.users.users(page=1)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}], 'users_total': 0, 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get user

*Detail information of a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersget)*

**Parameters:**

- **user_id** (int): ID of user. If you do not specify the user_id, you will get info about current user

**Example:**

```python
response = forum.users.get(user_id=2410024)
print(response.json())
```

```python
{'user': {'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Edit user

*Edit a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersedit)*

**Parameters:**

- **user_id** (int): ID of user. If you do not specify the user_id, you will edit current user
- **password** (str): New password.
- **password_old** (str): Data of the existing password, it is not required if (1) the current authenticated user has user admin permission, (2) the admincp scope is granted and (3) the user being edited is not the current authenticated user.
- **password_algo** (str): Algorithm used to encrypt the password and password_old parameters.
- **user_email** (str): New email of the user.
- **username** (str): New username of the user. 
  > Changing username requires Administrator permission.
- **user_title** (str): New custom title of the user.
- **primary_group_id** (int): ID of new primary group.
- **secondary_group_ids** (list[int]): Array of ID's of new secondary groups.
- **user_dob_day** (int): Date of birth (day) of the new user.
- **user_dob_month** (int): Date of birth (month) of the new user.
- **user_dob_year** (int): Date of birth (year) of the new user.
- **fields** (dict): Array of values for user fields.

**Example:**

```python
response = forum.users.edit(user_id=2410024, user_title="LOLZTEAM python -> zelenka.guru/threads/5523020")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get user fields

*List of user fields.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetfields)*

**Example:**

```python
response = forum.users.fields()
print(response.json())
```

```python
{'fields': [{'id': 'string', 'title': 'string', 'description': 'string', 'position': 'string', 'is_required': True, 'is_multi_choice': True, 'choices': [{'key': 'string', 'value': 'string'}]}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Search users

*Filtered list of users by username, email or custom fields.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetfiltered)*

**Parameters:**

- **username** (str): Username to filter. Usernames start with the query will be returned.
- **user_email** (str): Email to filter. Requires admincp scope.
- **custom_fields** (dict): Custom fields to filter. Example

**Example:**

```python
response = forum.users.search(username=2410024)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Lost password

*Request a password reset via email. Either username or email parameter must be provided. If both are provided, username will be used.*

*[Official documentation reference](https://lolzteam.readme.io/reference/userslostpassword)*

**Parameters:**

- **oauth_token** (str): A valid one time token.
- **username** (str): Username
- **email** (str): Email

**Example:**

```python
response = forum.users.lost_password(oauth_token=oauth, username="AS7RID")
print(response.json())
```

```python
{'status': 'ok', 'message': 'A password reset request has been emailed to you. Please follow the instructions in that email.'}
```

### Get user followings

*List of users whom are followed by a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetfollowedbyuser)*

**Parameters:**

- **user_id** (int): ID of user. If you do not specify the user_id, you will get followings users by current user
- **order** (str): Ordering of users. Support
- **page** (int): Page number of users.
- **limit** (int): Number of users in a page.

**Example:**

```python
response = forum.users.followings(user_id=2410024)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}], 'users_total': 0, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get user followers

*List of a user's followers.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetuserfollowers)*

**Parameters:**

- **user_id** (int): ID of user.
  > If you do not specify the user_id, you will get followers of current user
- **order** (str): Ordering of followers. 
- **page** (int): Page number of followers.
- **limit** (int): Number of followers in a page.

**Example:**

```python
response = forum.users.followers(user_id=2410024)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}], 'users_total': 0, 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Follow user

*Follow a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersfollow)*

**Parameters:**

- **user_id** (int): ID of user

**Example:**

```python
response = forum.users.follow(user_id=2410024)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Unfollow user

*Unfollow a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersunfollow)*

**Parameters:**

- **user_id** (int): ID of user

**Example:**

```python
response = forum.users.unfollow(user_id=2410024)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get ignored users

*List of ignored users of current user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetignored)*

**Parameters:**

- **total** (bool): If included in the request, only the user count is returned as users_total.

**Example:**

```python
response = forum.users.ignored()
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string'}]}
```

### Ignore user

*Ignore a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersignore)*

**Parameters:**

- **user_id** (int): ID of user

**Example:**

```python
response = forum.users.ignore(user_id=2410024)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Unignore user

*Unignore a user.*

*[Official documentation reference](https://lolzteam.readme.io/reference/usersunignore)*

**Parameters:**

- **user_id** (int): ID of user

**Example:**

```python
response = forum.users.unignore(user_id=2410024)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get user groups

*List of a user's groups.*
  > You can get groups only for current user. 
  > 
  > If you want to get another user groups you need scope admincp
  >
  > You can get main user group with "[Get user](#get-user)" method

*[Official documentation reference](https://lolzteam.readme.io/reference/usersgetusergroups)*

**Parameters:**

- **user_id** (int): ID of user. If user_id skipped, method will return current user groups

**Example:**

```python
response = forum.users.groups(user_id=2410024)
print(response.json())
```

```python
{'user_groups': [{'user_group_id': 0, 'user_group_title': 'string', 'is_primary_group': True}], 'user_id': 0}
```

# Profile posts

---

## Profile post comments

### Get profile post comments

*List of comments of a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsgetcomments)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **before** (int): Date to get older comments. 
  > Please note that this entry point does not support the page parameter, but it still does support limit.
- **limit** (int): Number of profile posts in a page.

**Example:**

```python
response = forum.profile_posts.comments.comments(profile_post_id=3223590)
print(response.json())
```

```python
{'comments': [{'comment_id': 0, 'profile_post_id': 0, 'comment_user_id': 0, 'comment_username': 'string', 'comment_create_date': 0, 'comment_body': 'string', 'user_is_ignored': True, 'timeline_user_id': 0, 'links': {'detail': 'string', 'profile_post': 'string', 'timeline': 'string', 'timeline_user': 'string', 'poster': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'delete': True}}], 'comments_total': 0, 'profile_post': {'profile_post_id': 0, 'timeline_user_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_like_count': 0, 'post_comment_count': 0, 'timeline_username': 'string', 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'links': {'permalink': 'string', 'detail': 'string', 'timeline': 'string', 'timeline_user': 'string', 'poster': 'string', 'likes': 'string', 'comments': 'string', 'report': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'like': True, 'comment': True, 'report': True}}, 'timeline_user': {'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get profile post comment

*Detail information of a profile post comment.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsgetcomment)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **comment_id** (int): ID of profile post comment

**Example:**

```python
response = forum.profile_posts.comments.get(profile_post_id=3223590,comment_id=1780307)
print(response.json())
```

```python
{'comment': {'comment_id': 0, 'profile_post_id': 0, 'comment_user_id': 0, 'comment_username': 'string', 'comment_create_date': 0, 'comment_body': 'string', 'user_is_ignored': True, 'timeline_user_id': 0, 'links': {'detail': 'string', 'profile_post': 'string', 'timeline': 'string', 'timeline_user': 'string', 'poster': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'delete': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create profile post comment

*Create a new profile post comment.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostscreatecomment)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **comment_body** (str): Content of the new profile post comment.

**Example:**

```python
response = forum.profile_posts.comments.create(profile_post_id=3223590,comment_body="Api example")
print(response.json())
```

```python
{'comment': {'comment_id': 0, 'profile_post_id': 0, 'comment_user_id': 0, 'comment_username': 'string', 'comment_create_date': 0, 'comment_body': 'string', 'user_is_ignored': True, 'timeline_user_id': 0, 'links': {'detail': 'string', 'profile_post': 'string', 'timeline': 'string', 'timeline_user': 'string', 'poster': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'delete': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Delete profile post comment

*Delete a profile post's comment.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsdeletecomment)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **comment_id** (int): ID of profile post comment
- **reason** (str): Reason of the report.

**Example:**

```python
response = forum.profile_posts.comments.delete(profile_post_id=3223590,comment_id=1780307,reason="No reason:c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

---

### Get profile posts

*List of profile posts (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsgetprofileposts)*

**Parameters:**

- **user_id** (int): ID of user.
- **page** (int): Page number of contents.
- **limit** (int): Number of contents in a page.

**Example:**

```python
response = forum.profile_posts.get_posts(user_id=2410024)
print(response.json())
```

```python
{'data':[{'content_type':'string','content_id':0,'post_id':0,'thread_id':0,'poster_user_id':0,'poster_username':'string','post_create_date':0,'post_body':'string','post_body_html':'string','post_body_plain_text':'string','signature':'string','signature_html':'string','signature_plain_text':'string','post_like_count':0,'post_attachment_count':0,'like_users':[{'user_id':0,'username':'string','display_style_group_id':0,'is_banned':0,'uniq_username_css':'string'}],'user_is_ignored':True,'post_is_published':True,'post_is_deleted':True,'post_update_date':0,'post_is_first_post':True,'links':{'permalink':'string','detail':'string','thread':'string','poster':'string','likes':'string','report':'string','attachments':'string','poster_avatar':'string'},'permissions':{'view':True,'edit':True,'delete':True,'reply':True,'like':True,'report':True,'upload_attachment':True},'thread':{'thread_id':0,'forum_id':0,'thread_title':'string','thread_view_count':0,'creator_user_id':0,'creator_username':'string','thread_create_date':0,'thread_update_date':0,'user_is_ignored':True,'thread_post_count':0,'thread_is_published':True,'thread_is_deleted':True,'thread_is_sticky':True,'thread_is_followed':True,'thread_prefixes':[{'prefix_id':0,'prefix_title':'string'}],'thread_tags':{'3':'string','49306':'string'},'links':{'permalink':'string','detail':'string','followers':'string','forum':'string','posts':'string','first_poster':'string','first_poster_avatar':'string','first_post':'string','last_poster':'string','last_post':'string'},'permissions':{'view':True,'delete':True,'follow':True,'post':True,'upload_attachment':True}}}],'data_total':0,'user':{'user_id':0,'username':'string','user_message_count':0,'user_register_date':0,'user_like_count':0,'short_link':'string','user_title':'string','user_is_valid':True,'user_is_verified':True,'user_is_followed':True,'user_last_seen_date':0,'links':{'permalink':'string','detail':'string','avatar':'string','avatar_big':'string','avatar_small':'string','followers':'string','followings':'string','ignore':'string','timeline':'string'},'permissions':{'edit':True,'follow':True,'ignore':True,'profile_post':True},'user_is_ignored':True,'user_is_visitor':True,'user_group_id':0,'custom_fields':{'discord':'string','jabber':'string','lztAwardUserTrophy':'string','lztCuratorNodeTitle':'string','lztCuratorNodeTitleEn':'string','lztInnovation20Link':'string','lztInnovation30Link':'string','lztInnovationLink':'string','lztSympathyIncreasing':'string','lztSympathyZeroing':'string','qiwi':'string','scamURL':'string','steam':'string','telegram':'string','vk':'string'}},'links':{'pages':0,'page':0,'next':'string'},'system_info':{'visitor_id':0,'time':0}}
```

### Get profile post

*Detail information of a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsget)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.

**Example:**

```python
response = forum.profile_posts.get(profile_post_id=2667951)
print(response.json())
```

```python
{'profile_post': {'profile_post_id': 0, 'timeline_user_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_like_count': 0, 'post_comment_count': 0, 'timeline_username': 'string', 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'links': {'permalink': 'string', 'detail': 'string', 'timeline': 'string', 'timeline_user': 'string', 'poster': 'string', 'likes': 'string', 'comments': 'string', 'report': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'like': True, 'comment': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create profile post

*Create a new profile post on a user timeline.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostscreate)*

**Parameters:**

- **post_body** (str): Content of the new profile post.
- **user_id** (int): ID of user. If you do not specify the user_id, you will create profile post in current user's timeline

**Example:**

```python
response = forum.profile_posts.create(user_id=2410024,post_body="Api example")
print(response.json())
```

```python
{'data': {'content_type': 'string', 'content_id': 0, 'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}, 'thread': {'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'thread_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}], 'thread_tags': {'3': 'string', '49306': 'string'}, 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True}}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Edit profile post

*Edit a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsedit)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **post_body** (str): New content of the profile post.

**Example:**

```python
response = forum.profile_posts.edit(profile_post_id=2667951,post_body="Api example")
print(response.json())
```

```python
{'profile_post': {'profile_post_id': 0, 'timeline_user_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_like_count': 0, 'post_comment_count': 0, 'timeline_username': 'string', 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'links': {'permalink': 'string', 'detail': 'string', 'timeline': 'string', 'timeline_user': 'string', 'poster': 'string', 'likes': 'string', 'comments': 'string', 'report': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'like': True, 'comment': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Delete profile post

*Delete a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsdelete)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **reason** (str): Reason of the profile post removal.

**Example:**

```python
response = forum.profile_posts.delete(profile_post_id=2667951,reason="No reason:c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Get profile post likes

*List of users who liked a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsgetlikedusers)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.

**Example:**

```python
response = forum.profile_posts.likes(profile_post_id=2667951)
print(response.json())
```

```python
{'users': [{'user_id': 0, 'username': 'string'}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Like profile post

*Like a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostslike)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.

**Example:**

```python
response = forum.profile_posts.like(profile_post_id=2667951)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Unlike profile post

*Unlike a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsunlike)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.

**Example:**

```python
response = forum.profile_posts.unlike(profile_post_id=2667951)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Report profile post

*Report a profile post.*

*[Official documentation reference](https://lolzteam.readme.io/reference/profilepostsreport)*

**Parameters:**

- **profile_post_id** (int): ID of profile post.
- **message** (str): Reason of the report.

**Example:**

```python
response = forum.profile_posts.report(profile_post_id=2667951, message="No reason:c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

# Conversations

---

## Conversation messages

### Get conversation messages

*List of messages in a conversation (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsgetmessages)*

**Parameters:**

- **conversation_id** (int): ID of conversation.
- **page** (int): Page number of messages.
- **limit** (int): Number of messages in a page.
- **order** (str): Ordering of messages. Can be [natural, natural_reverse].
- **before** (int): Date to get older messages.
- **after** (int): Date to get newer messages.

**Example:**

```python
response = forum.conversations.messages.get_all(conversation_id=17312)
print(response.json())
```

```python
{'message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get conversation message

*Detail information of a message.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsgetmessage)*

**Parameters:**

- **message_id** (int): ID of conversation message.

**Example:**

```python
response = forum.conversations.messages.get(message_id=1731221)
print(response.json())
```

```python
{'message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Send conversation message

*Create a new conversation message.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationscreatemassage)*

**Parameters:**

- **conversation_id** (int): ID of conversation.
- **message_body** (str): Content of the new message.

**Example:**

```python
response = forum.conversations.messages.create(conversation_id=17312,message_body="Api example")
print(response.json())
```

```python
{'message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Edit conversation message

*Edit a message.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationseditmessage)*

**Parameters:**

- **message_id** (int): ID of conversation message.
- **message_body** (str): New content of the message.

**Example:**

```python
response = forum.conversations.messages.edit(message_id=1731221, message_body="Api example1")
print(response.json())
```

```python
{'message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Delete conversation message

*Delete a message.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsdeletemessage)*

**Parameters:**

- **message_id** (int): ID of conversation message.

**Example:**

```python
response = forum.conversations.messages.delete(message_id=1731221)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Report conversation message

*Report a message.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsreportmessage)*

**Parameters:**

- **message_id** (int): ID of conversation message.
- **message** (str): Reason of the report.

**Example:**

```python
response = forum.conversations.messages.report(message_id=1731221,message="No reason:c")
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

---

### Get conversations

*List of conversations (with pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsgetall)*

**Parameters:**

- **page** (int): Page number of conversations.
- **limit** (int): Number of conversations in a page.

**Example:**

```python
response = forum.conversations.get_all()
print(response.json())
```

```python
{'conversations': [{'conversation_id': 0, 'conversation_title': 'string', 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'conversation_create_date': 0, 'conversation_update_date': 0, 'is_starred': 0, 'is_group': 0, 'user_is_ignored': True, 'conversation_message_count': 0, 'conversation_has_new_message': True, 'links': {'permalink': 'string', 'detail': 'string', 'messages': 'string'}, 'permissions': {'reply': True, 'delete': True, 'upload_attachment': True}, 'first_message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'recipients': [{'user_id': 0, 'username': 'string', 'username_html': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'last_activity': 0, 'is_online': True}]}], 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get conversation

*Detail information of a conversation.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsget)*

**Parameters:**

- **conversation_id** (int): ID of conversation.

**Example:**

```python
response = forum.conversations.get(conversation_id=17312)
print(response.json())
```

```python
{'conversation': {'conversation_id': 0, 'conversation_title': 'string', 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'conversation_create_date': 0, 'conversation_update_date': 0, 'is_starred': 0, 'is_group': 0, 'user_is_ignored': True, 'conversation_message_count': 0, 'conversation_has_new_message': True, 'links': {'permalink': 'string', 'detail': 'string', 'messages': 'string'}, 'permissions': {'reply': True, 'delete': True, 'upload_attachment': True}, 'first_message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'recipients': [{'user_id': 0, 'username': 'string', 'username_html': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'last_activity': 0, 'is_online': True}]}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create conversation

*Create a new conversation.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationscreate)*

**Parameters:**

- **recipient_id** (int): ID of recipient.
- **message** (str): First message in conversation.
- **open_invite** (bool): Allow invites in conversation.
- **conversation_locked** (bool): Is conversation locked.
- **allow_edit_messages** (bool): Allow edit messages.

**Example:**

```python
response = forum.conversations.create(recipient_id=2410024, message="Api example")
print(response.json())
```

```python
{'conversation': {'conversation_id': 0, 'conversation_title': 'string', 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'conversation_create_date': 0, 'conversation_update_date': 0, 'is_starred': 0, 'is_group': 0, 'user_is_ignored': True, 'conversation_message_count': 0, 'conversation_has_new_message': True, 'links': {'permalink': 'string', 'detail': 'string', 'messages': 'string'}, 'permissions': {'reply': True, 'delete': True, 'upload_attachment': True}, 'first_message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'recipients': [{'user_id': 0, 'username': 'string', 'username_html': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'last_activity': 0, 'is_online': True}]}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Create group conversation

*Create a new group conversation.*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationscreate)*

**Parameters:**

- **recipients** (str): List of usernames (Separated by comma. Example -> "RaysMorgan,Thomas,Requeste")
- **title** (str): The title of new conversation.
- **message** (str): First message in conversation.
- **open_invite** (bool): Allow invites in conversation.
- **conversation_locked** (bool): Is conversation locked.
- **allow_edit_messages** (bool): Allow edit messages.

**Example:**

```python
response = forum.conversations.create_group(recipients="AS7RID", message="Api example")
print(response.json())
```

```python
{'conversation': {'conversation_id': 0, 'conversation_title': 'string', 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'conversation_create_date': 0, 'conversation_update_date': 0, 'is_starred': 0, 'is_group': 0, 'user_is_ignored': True, 'conversation_message_count': 0, 'conversation_has_new_message': True, 'links': {'permalink': 'string', 'detail': 'string', 'messages': 'string'}, 'permissions': {'reply': True, 'delete': True, 'upload_attachment': True}, 'first_message': {'message_id': 0, 'conversation_id': 0, 'creator_user_id': 0, 'creator_username': 'string', 'creator_username_html': 'string', 'message_create_date': 0, 'message_body': 'string', 'message_body_html': 'string', 'message_body_plain_text': 'string', 'message_attachment_count': 0, 'user_is_ignored': True, 'links': {'detail': 'string', 'conversation': 'string', 'creator': 'string', 'creator_avatar': 'string', 'report': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'upload_attachment': True, 'report': True}}, 'recipients': [{'user_id': 0, 'username': 'string', 'username_html': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'last_activity': 0, 'is_online': True}]}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Leave from conversation

*Leave from conversation*

*[Official documentation reference](https://lolzteam.readme.io/reference/conversationsdelete)*

**Parameters:**

- **conversation_id** (int): ID of conversation.
- **leave_type** (str): Leave type. Can be ["delete","delete_ignore"].

**Example:**

```python
response = forum.conversations.leave(conversation_id=17312)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

# Notifications

### Get notifications

*List of notifications (both read and unread).*

*[Official documentation reference](https://lolzteam.readme.io/reference/notificationsgetall)*

**Example:**

```python
response = forum.notifications.get_all()
print(response.json())
```

```python
{'notifications': [{'notification_id': 0, 'notification_create_date': 0, 'content_type': 'string', 'content_id': 0, 'content_action': 'string', 'notification_is_unread': True, 'creator_user_id': 0, 'creator_username': 'string', 'notification_type': 'string', 'links': {'content': 'string', 'creator_avatar': 'string'}, 'notification_html': 'string'}], 'notifications_total': 0, 'links': {'read': 'string', 'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get notification

*Get associated content of notification. The response depends on the content type.*

*[Official documentation reference](https://lolzteam.readme.io/reference/notificationsget)*

**Parameters:**

- **notification_id** (int): ID of notification.

**Example:**

```python
response = forum.notifications.get(notification_id=1590600042)
print(response.json())
```

```python
{'notification': {'notification_id': 0, 'notification_create_date': 0, 'content_type': 'string', 'content_id': 0, 'content_action': 'string', 'notification_is_unread': True, 'creator_user_id': 0, 'creator_username': 'string', 'notification_type': 'string', 'links': {'content': 'string', 'creator_avatar': 'string'}, 'notification_html': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Read notification/s

*Mark single notification or all existing notifications read.*

*[Official documentation reference](https://lolzteam.readme.io/reference/notificationsmarkread)*

**Parameters:**

- **notification_id** (int): ID of notification. If notification_id is omitted, it's mark all existing notifications as read.

**Example:**

```python
response = forum.notifications.read(notification_id=1590600042)
print(response.json())
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

### Send custom notificaton

*Send a custom alert.*
  > The current user must have the [bd] API: Send custom alert permission
  > 
  > You can't use that method :c

*[Official documentation reference](https://lolzteam.readme.io/reference/notificationssendcustom)*

**Parameters:**

- **user_id** (int): The alert receiver.
- **username** (str): The alert receiver.
- **message** (str): The alert message.
- **message_html** (str): The alert message.
- **notification_type** (str): The notification type.
- **extra_data** (str): Extra data when sending alert. Предположительно это словарик, но я не уверен

**Example:**

```python
response = forum.notifications.custom(user_id=1, message="Hello grisha", notification_type="user")
print(response.json())
```

```python
string
```

# Categories

### Get categories

*List of all categories in the system.*

*[Official documentation reference](https://lolzteam.readme.io/reference/categoriesgetcategories)*

**Parameters:**

- **parent_category_id** (int): ID of parent category.
- **parent_forum_id** (int): ID of parent forum.
- **order** (str): Ordering of categories.

**Example:**

```python
response = forum.categories.get_categories()
print(response.json())
```

```python
{'categories': [{'category_id': 0, 'category_title': 'string', 'category_description': 'string', 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True}}], 'categories_total': 0, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get category

*Detail information of a category.*

*[Official documentation reference](https://lolzteam.readme.io/reference/categoriesgetcategory)*

**Parameters:**

- **category_id** (int): ID of category

**Example:**

```python
response = forum.categories.get_category(category_id=103)
print(response.json())
```

```python
{'category': {'category_id': 0, 'category_title': 'string', 'category_description': 'string', 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

# Pages

### Get pages

*List of all pages in the system.*

*[Official documentation reference](https://lolzteam.readme.io/reference/pagesgetpages)*

**Parameters:**

- **parent_page_id** (int): ID of parent page. If exists, filter pages that are direct children of that page.
- **order** (str): Ordering of pages. Can be [natural, list]

**Example:**

```python
response = forum.pages.get_pages()
print(response.json())
```

```python
{'pages': [{'page_id': 0, 'page_title': 'string', 'page_description': 'string', 'links': {'permalink': 'string', 'detail': 'string', 'sub-pages': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True}}], 'pages_total': 0, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get page

*Detail information of a page.*

*[Official documentation reference](https://lolzteam.readme.io/reference/pagesgetpage)*

**Parameters:**

- **page_id** (int): ID of parent page. If exists, filter pages that are direct children of that page.

**Example:**

```python
response = forum.pages.get_page(page_id=693)
print(response.json())
```

```python
{'page': {'page_id': 0, 'page_title': 'string', 'page_description': 'string', 'links': {'permalink': 'string', 'detail': 'string', 'sub-pages': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

# Tags

### Get popular tags

*List of popular tags (no pagination).*

*[Official documentation reference](https://lolzteam.readme.io/reference/contenttagginggetpopular)*

**Parameters:**


**Example:**

```python
response = forum.tags.popular()
print(response.json())
```

```python
{'tag': {'1': 'string', '2': 'string', '3': 'string', '4': 'string', '5': 'string', '6': 'string', '7': 'string', '8': 'string', '9': 'string', '10': 'string', '11': 'string', '12': 'string', '14': 'string', '15': 'string', '16': 'string', '17': 'string', '18': 'string', '19': 'string', '20': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Get tags

*List of tags.*

*[Official documentation reference](https://lolzteam.readme.io/reference/contenttagginggetpopular)*

**Parameters:**

- **page** (int): Page number of tags list.
- **limit** (int): Limit of tags on a page.

**Example:**

```python
response = forum.tags.tags(page=7)
print(response.json())
```

```python
{'tags': {'1': 'string', '2': 'string', '3': 'string', '4': 'string', '5': 'string', '6': 'string', '7': 'string', '8': 'string', '9': 'string', '10': 'string', '11': 'string', '12': 'string', '14': 'string', '15': 'string', '16': 'string', '17': 'string', '18': 'string', '19': 'string', '20': 'string'}, 'tags_total': 0, 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Tagged contents

*List of tagged contents.*

*[Official documentation reference](https://lolzteam.readme.io/reference/contenttagginggetcontents)*

**Parameters:**

- **tag_id** (int): Id of tag.
- **page** (int): Page number of tags list.
- **limit** (int): Number of tagged contents in a page.

**Example:**

```python
response = forum.tags.tagged(tag_id=20)
print(response.json())
```

```python
{'tag': {'tag_id': 0, 'tag_text': 'string', 'tag_use_count': 0, 'links': {'permalink': 'string', 'detail': 'string'}}, 'tagged': [{'content_type': 'string', 'content_id': 0, 'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': ['string'], 'thread_tags': {'14': 'string', '101': 'string', '355': 'string', '1097': 'string'}, 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': ['string'], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'tagged_total': 0, 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Find tags

*Filtered list of tags.*

*[Official documentation reference](https://lolzteam.readme.io/reference/contenttagginggetfilteredcontent)*

**Parameters:**

- **tag** (str): tag to filter. Tags start with the query will be returned.

**Example:**

```python
response = forum.tags.find(tag="LOLZTEAM")
print(response.json())
```

```python
{'tags': ['string'], 'ids': [0], 'system_info': {'visitor_id': 0, 'time': 0}}
```

# Search

### Search for threads

*Search for threads.*

*[Official documentation reference](https://lolzteam.readme.io/reference/searchingthreads)*

**Parameters:**

- **q** (str): Search query. 
  > Can be skipped if user_id is set.
- **tag** (str): Tag to search for tagged contents.
- **forum_id** (int): ID of the container forum to search for contents. 
  > Child forums of the specified forum will be included in the search.
- **user_id** (int): ID of the creator to search for contents.
- **page** (int): Page number of results.
- **limit** (int): Number of results in a page.
- **data_limit** (int): Number of thread data to be returned.

**Example:**

```python
response = forum.search.thread(q="LOLZTEAM")
print(response.json())
```

```python
{'threads': [{'thread_id': 0}], 'data': [{'content_type': 'string', 'content_id': 0, 'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Search for posts

*Search for posts.*

*[Official documentation reference](https://lolzteam.readme.io/reference/searchingposts)*

**Parameters:**

- **q** (str): Search query. 
  > Can be skipped if user_id is set.
- **tag** (str): Tag to search for tagged contents.
- **forum_id** (int): ID of the container forum to search for contents. 
  > Child forums of the specified forum will be included in the search.
- **user_id** (int): ID of the creator to search for contents.
- **page** (int): Page number of results.
- **limit** (int): Number of results in a page.
- **data_limit** (int): Number of thread data to be returned.

**Example:**

```python
response = forum.search.post(q="LOLZTEAM")
print(response.json())
```

```python
{'posts': [{'thread_id': 0, 'post_id': 0}], 'data': [{'content_type': 'string', 'content_id': 0, 'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### profile_posts

*Search for threads.*

**Parameters:**

- **q** (str): Search query. Can be skipped if user_id is set.
- **user_id** (int): ID of the creator to search for contents.
- **page** (int): Page number of results.
- **limit** (int): Number of results in a page.

**Example:**

```python
response = forum.search.profile_posts(user_id=2410024)
print(response.json())
```

```python
{'data': [{'content_type': 'string', 'content_id': 0, 'profile_post_id': 0, 'timeline_user_id': 0, 'poster_user_id': 'string', 'poster_username': 0, 'poster_username_html': 0, 'post_create_date': 'string', 'post_body': 0, 'post_like_count': 0}], 'data_total': 0, 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Search for all types of content

*Search for all types of content.*

*[Official documentation reference](https://lolzteam.readme.io/reference/searchingallcontents)*

**Parameters:**

- **q** (str): Search query. 
  > Can be skipped if user_id is set.
- **tag** (str): Tag to search for tagged contents.
- **forum_id** (int): ID of the container forum to search for contents. 
  > Child forums of the specified forum will be included in the search.
- **user_id** (int): ID of the creator to search for contents.
- **page** (int): Page number of results.
- **limit** (int): Number of results in a page.

**Example:**

```python
response = forum.search.post(q="LOLZTEAM")
print(response.json())
```

```python
{'posts': [{'thread_id': 0, 'post_id': 0}], 'data': [{'content_type': 'string', 'content_id': 0, 'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Search for tagged

*Search for tagged contents.*

*[Official documentation reference](https://lolzteam.readme.io/reference/searchingtagged)*

**Parameters:**

- **tag** (str): Tag to search for tagged contents.
- **tags** (list[str]): Array of tags to search for tagged contents.
- **page** (int): Page number of results.
- **limit** (int): Number of results in a page.

**Example:**

```python
response = forum.search.tag(tag="LOLZTEAM")
print(response.json())
```

```python
{'posts': [{'thread_id': 0, 'post_id': 0}], 'data': [{'content_type': 'string', 'content_id': 0, 'thread_id': 0, 'forum_id': 0, 'thread_title': 'string', 'thread_view_count': 0, 'creator_user_id': 0, 'creator_username': 'string', 'thread_create_date': 0, 'thread_update_date': 0, 'user_is_ignored': True, 'thread_post_count': 0, 'thread_is_published': True, 'thread_is_deleted': True, 'thread_is_sticky': True, 'thread_is_followed': True, 'first_post': {'post_id': 0, 'thread_id': 0, 'poster_user_id': 0, 'poster_username': 'string', 'post_create_date': 0, 'post_body': 'string', 'post_body_html': 'string', 'post_body_plain_text': 'string', 'signature': 'string', 'signature_html': 'string', 'signature_plain_text': 'string', 'post_like_count': 0, 'post_attachment_count': 0, 'like_users': [{'user_id': 0, 'username': 'string', 'display_style_group_id': 0, 'is_banned': 0, 'uniq_username_css': 'string'}], 'user_is_ignored': True, 'post_is_published': True, 'post_is_deleted': True, 'post_update_date': 0, 'post_is_first_post': True, 'links': {'permalink': 'string', 'detail': 'string', 'thread': 'string', 'poster': 'string', 'likes': 'string', 'report': 'string', 'attachments': 'string', 'poster_avatar': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'reply': True, 'like': True, 'report': True, 'upload_attachment': True}}, 'thread_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}], 'thread_tags': ['string'], 'links': {'permalink': 'string', 'detail': 'string', 'followers': 'string', 'forum': 'string', 'posts': 'string', 'first_poster': 'string', 'first_poster_avatar': 'string', 'first_post': 'string', 'last_poster': 'string', 'last_post': 'string'}, 'permissions': {'view': True, 'delete': True, 'follow': True, 'post': True, 'upload_attachment': True, 'edit': True}, 'forum': {'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': [{'group_title': 'string', 'group_prefixes': [{'prefix_id': 0, 'prefix_title': 'string'}]}], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'forum_is_followed': True}}], 'links': {'pages': 0, 'page': 0, 'next': 'string'}, 'system_info': {'visitor_id': 0, 'time': 0}}
```

### Search indexing

*Index external content data into search system to be searched later.*

*[Official documentation reference](https://lolzteam.readme.io/reference/batchrequestssearchindexing)*

**Parameters:**

- **content_type** (str): The type of content being indexed.
- **content_id** (str):  The unique id for the content.
- **title** (str):  Content title.
- **body** (str):  Content body.
- **link** (str):  Link related to content.
- **date** (int): Unix timestamp in second of the content. If missing, current time will be used.

**Example:**

```python
response = forum.search.indexing(content_type="post",content_id=40767586,title="LOLZTEAM Python",body="Body",link="https://zelenka.guru/threads/5523020/")
print(response.text)
```

```python
{'status': 'ok', 'message': 'Changes Saved'}
```

# Oauth

### Facebook oauth

*Request API access token using Facebook access token. Please note that because Facebook uses app-scoped user_id, it is not possible to recognize user across different Facebook Applications.*

*[Official documentation reference](https://lolzteam.readme.io/reference/oauthfacebook)*

**Parameters:**

- **client_id** (int): ID of facebook client.
- **client_secret** (str): Secret phrase of facebook client.
- **facebook_token** (str): Facebook token.

**Example:**

```python
response = forum.oauth.facebook(client_id="client_id",client_secret="client_secret",facebook_token="fb_token")
print(response.text)
```

```python
string
```

### Twitter oauth

*Request API access token using Twitter access token. The twitter_uri and twitter_auth parameters are similar to X-Auth-Service-Provider and X-Verify-Credentials-Authorization as specified in Twitter's OAuth Echo specification.*

*[Official documentation reference](https://lolzteam.readme.io/reference/oauthtwitter)*

**Parameters:**

- **client_id** (int): ID of twitter client.
- **client_secret** (str): Secret phrase of twitter client.
- **twitter_url** (str): "the full /account/verify_credentials.json uri that has been used to calculate OAuth signature. For security reason, the uri must use HTTPS protocol and the hostname must be either "twitter.com" or "twitter.com"."
- **twitter_auth** (str): the complete authentication header that starts with "OAuth". Consult Twitter document for more information.

**Example:**

```python
response = forum.oauth.twitter(client_id="client_id",client_secret="client_secret",twitter_url="https://twitter_url",twitter_auth="twitter_auth")
print(response.text)
```

```python
string
```

### Google oauth

*Request API access token using Google access token.*

*[Official documentation reference](https://lolzteam.readme.io/reference/oauthgoogle)*

**Parameters:**

- **client_id** (int): ID of facebook client.
- **client_secret** (str): Secret phrase of facebook client.
- **google_token** (str): Google token.

**Example:**

```python
response = forum.oauth.google(client_id="client_id",client_secret="client_secret",google_token="google_token")
print(response.text)
```

```python
string
```

### Associate oauth

*Request API access token and associate social account with an existing user account.*

*[Official documentation reference](https://lolzteam.readme.io/reference/oauthassociate)*

**Parameters:**

- **client_id** (int): ID of associate client.
- **user_id** (str): ID of user.
- **password** (str): Can be used with password_algo for better security. See Encryption section for more information.
- **extra_data** (str): Extra data
- **extra_timestamp** (int): Extra timestamp

**Example:**

```python
response = forum.oauth.associate(client_id="client_id",client_secret="client_secret",user_id="user_id",password="user_pass", extra_data="data",extra_timestamp="timestamp")
print(response.text)
```

```python
string
```

### Admin oauth

*Request API access token for another user.*
  > This requires admincp scope and the current user must have sufficient system permissions.*

*[Official documentation reference](https://lolzteam.readme.io/reference/oauthadmin)*
**Parameters:**

- **user_id** (int): ID of the user that needs access token.

**Example:**

```python
response = forum.oauth.admin(user_id=1)
print(response.json())
```

```python
string
```

# Navigation

*List of navigation elements within the system.*

*[Official documentation reference](https://lolzteam.readme.io/reference/navigationgetnavigation)*

**Parameters:**

- **parent** (int): ID of parent element.
  > If exists, filter elements that are direct children of that element.

**Example:**

```python
response = forum.navigation()
print(response.json())
```

```python
{'elements': [{'category_id': 0, 'category_title': 'string', 'category_description': 'string', 'links': {'permalink': 'string', 'detail': 'string', 'sub-categories': 'string', 'sub-forums': 'string', 'sub-elements': 'string', 'threads': 'string', 'followers': 'string'}, 'permissions': {'view': True, 'edit': True, 'delete': True, 'create_thread': True, 'upload_attachment': True, 'tag_thread': True, 'follow': True}, 'navigation_type': 'string', 'navigation_id': 0, 'navigation_parent_id': 0, 'has_sub_elements': True, 'forum_id': 0, 'forum_title': 'string', 'forum_description': 'string', 'forum_thread_count': 0, 'forum_post_count': 0, 'forum_prefixes': ['string'], 'thread_default_prefix_id': 0, 'thread_prefix_is_required': True, 'forum_is_followed': True}]}
```

# Get batch job

*Creates batch job for Batch method*

**Parameters:**

- **func** (function): Target function.
- **job_name** (str): Job name.
- ****kwargs** (str): Target function parameters.

**Example:**

```python
jobs = [
    CreateJob(forum.users.search, job_name="1", custom_fields={"telegram": "AS7RID"}),
    CreateJob(forum.users.get, job_name="2", user_id=1),
    CreateJob(forum.threads.get, job_name="3", thread_id=5523020),
    CreateJob(forum.threads.create, job_name="4", forum_id=876, thread_title="Api batch example",post_body="Api batch example body", thread_tags="LOLZTEAM")
]
for job in jobs:
    print(job)
```

```python
{'id': '1', 'uri': 'https://zelenka.guru/users/find', 'method': 'GET', 'params': {'username': None, 'user_email': None, 'custom_fields[telegram]': 'AS7RID', 'custom_fields': {'telegram': 'AS7RID'}, 'locale': 'en'}, 'data': {'username': None, 'user_email': None, 'custom_fields[telegram]': 'AS7RID', 'custom_fields': {'telegram': 'AS7RID'}}, 'files': None}
{'id': '2', 'uri': 'https://zelenka.guru/users/1', 'method': 'GET', 'params': {'locale': 'en'}, 'data': {}, 'files': None}
{'id': '3', 'uri': 'https://zelenka.guru/threads/5523020', 'method': 'GET', 'params': {'locale': 'en'}, 'data': {}, 'files': None}
{'id': '4', 'uri': 'https://zelenka.guru/threads', 'method': 'POST', 'params': {'forum_id': 876, 'thread_prefix_id': None, 'thread_tags': 'LOLZTEAM', 'thread_title': 'Api batch example', 'post_body': 'Api batch example body', 'locale': 'en'}, 'data': {'thread_title': 'Api batch example', 'post_body': 'Api batch example body', 'forum_id': 876, 'thread_prefix_id': None, 'thread_tags': 'LOLZTEAM'}, 'files': None}
```

# Batch

*Execute multiple API requests at once.*

  > Maximum batch jobs is 10.
  >
  > Forum batch can only proceed with forum url's. If you want to use batch with market url's try [this](https://github.com/AS7RIDENIED/LOLZTEAM/blob/main/Documentation/Market.md#batch)

*[Official documentation reference](https://lolzteam.readme.io/reference/batchrequestsexecute)*

**Parameters:**

- **jobs** (list[dict]): List of batch jobs.

**Example:**

```python
jobs = [
    CreateJob(forum.users.search, job_name="1", custom_fields={"telegram": "AS7RID"}),
    CreateJob(forum.users.get, job_name="2", user_id=1),
    CreateJob(forum.threads.get, job_name="3", thread_id=5523020),
    CreateJob(forum.threads.create, job_name="4", forum_id=876, thread_title="Api batch example",post_body="Api batch example body", thread_tags="LOLZTEAM")
]
response = forum.batch(jobs=jobs)
for job_name, job_data in response.json()["jobs"].items():
    print(job_data)
```

```python
{'_job_result': 'ok', 'users': [{'user_id': 2410024, 'username': 'AS7RID', 'username_html': '<span  class="style22">AS7RID</span>', 'user_message_count': 1089, 'user_register_date': 1560282271, 'user_like_count': 2949, 'short_link': 'as7rid', ... }
{'_job_result': 'ok', 'user': {'user_id': 1, 'username': 'RaysMorgan', 'username_html': '<span  class="style3">RaysMorgan</span>', 'user_message_count': 12104, 'user_register_date': 1362675475, 'user_like_count': 44351, 'short_link': 'rays',  ... }
{'_job_result': 'ok', 'thread': {'thread_id': 5523020, 'forum_id': 976, 'thread_title': 'Библиотека для упрощения работы с API | LOLZTEAM Forum/Market/Antipublic Python', 'thread_view_count': 715, 'creator_user_id': 2410024, 'creator_usern ... }
{'_job_result': 'ok', 'thread': {'thread_id': 5907641, 'forum_id': 876, 'thread_title': 'Api batch example', 'thread_view_count': 1, 'creator_user_id': 2410024, 'creator_username': 'AS7RID', 'creator_username_html': '<span  class="style22">AS ... }
```

# Send async

*Send request as async*

**Parameters:**

- **func** (function): Target function.
- ****kwargs** (any): Target function parameters.

**Example:**

```python
response = await SendAsAsync(func=forum.users.get, user_id=2410024)
print(response.json())
```

```python
{'user': {'user_id': 0, 'username': 'string', 'user_message_count': 0, 'user_register_date': 0, 'user_like_count': 0, 'short_link': 'string', 'user_title': 'string', 'user_is_valid': True, 'user_is_verified': True, 'user_is_followed': True, 'user_last_seen_date': 0, 'links': {'permalink': 'string', 'detail': 'string', 'avatar': 'string', 'avatar_big': 'string', 'avatar_small': 'string', 'followers': 'string', 'followings': 'string', 'ignore': 'string', 'timeline': 'string'}, 'permissions': {'edit': True, 'follow': True, 'ignore': True, 'profile_post': True}, 'user_is_ignored': True, 'user_is_visitor': True, 'user_group_id': 0, 'custom_fields': {'discord': 'string', 'jabber': 'string', 'lztAwardUserTrophy': 'string', 'lztCuratorNodeTitle': 'string', 'lztCuratorNodeTitleEn': 'string', 'lztInnovation20Link': 'string', 'lztInnovation30Link': 'string', 'lztInnovationLink': 'string', 'lztSympathyIncreasing': 'string', 'lztSympathyZeroing': 'string', 'qiwi': 'string', 'scamURL': 'string', 'steam': 'string', 'telegram': 'string', 'vk': 'string'}}, 'system_info': {'visitor_id': 0, 'time': 0}}
```