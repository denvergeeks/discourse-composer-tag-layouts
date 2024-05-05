_**This Theme Component for Discourse enables the author of a Topic to create a custom layout for any particular Topic by adding certain pre-defined tags which, when applied, selectively remove specific elements and sections of the layout for that Topic only.**_

#### Discussion and use-cases are described over on Meta:  [Create custom layouts for individual Topic Posts in Discourse](https://meta.discourse.org/t/page-publishing/151971/145)

[This version includes settings for a Help Popup when the tag **tag-layouts** is applied. A clickable link will appear in the botton right corner of the composer text area which pops up a modal containing all of the available tags which can be used, and what they do. (The contents of the modal can be changed in the component's settings, but it defaults to [https://denvergeeks.github.io/discourse-composer-tag-layouts/docs/](https://denvergeeks.github.io/discourse-composer-tag-layouts/docs/).) Code from https://meta.discourse.org/t/composer-tip-under-specific-tag-topics/255618 was integrated into this theme component in order to provide this functionality. (The site setting **characters required enabled** should be un-checked or it will hide the Help Popup link, as it occupies that same space in the composer text area.)]

## First things first...

## 1) Discourse default settings need some adjustments in order for this to work:

In your site's admin settings, search for **tag** and insure the following settings:

Required: ![discourse-setting-enable-tags-on-topics](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/16ac3d42-da04-4ea9-a497-742083100842)

Required: ![discourse-setting-max-tags-per-topic](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/d31eee90-1233-4925-b2b2-90fe6e4bde19)

Optional (Helpful for Admin): ![discourse-setting-default-navigation-menu-tags](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/ac3f44f0-6fb0-4bb5-b450-fca4f57e5248)

Required: ![discourse-setting-max-tag-length](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/e21170dd-ebe7-4753-878a-1556bb9216ff)

Optional (Helpful for Admin): ![discourse-setting-max-tags-search-result](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/aca6afcd-61a1-46c2-b6c2-28e56b05d422)

Optional (Helpful for Admin): ![discourse-setting-max-tags-in-filter-list](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/d88cead1-3152-4eec-a70a-083afa190f1a)

Optional (Helpful for Admin): ![discourse-setting-tags-sort-alphabetically](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/3c1fccdf-5e4a-4cd3-a15e-adcb4f6ce73a)

Optional (Helpful for Admin): ![discourse-setting-tags-listed-by-group](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/061356ad-658f-45b5-b0ef-21b29d1ab7ad)

Optional (Helpful for Admin): ![discourse-setting-force-lowercase-tags](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/c11b61a9-5ae8-45a3-a81e-1eb0edf9272c)

Optional (Helpful for Admin): ![discourse-setting-create-post-for-category-and-tag-changes](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/695b3cf2-e8ad-4e7a-ad91-3607781503e0)

Required: ![discourse-setting-show-tags-by-group](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/36979349-4a20-439e-85fc-bd977927b61c)

## 2) Secondly, you need to create 2 new Tag Groups so the Layout Tags will be hidden from (and won't needlessly clutter up) the Side Navigation Menu and the Tags Page:

![discourse-tag-groups-layout-tags-parent](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/63de082a-24e7-4b17-8b93-a3aaff0fa7f7)

![discourse-tag-groups-hide-with-tag-child-of-layout-tags-group](https://github.com/denvergeeks/discourse-composer-tag-layouts/assets/322529/1f2e0946-aacf-4a71-8cac-ac7696fe0575)

### Now your site should be ready to use the following Tags...

> For convenience, [here is a link to an HTML page](https://denvergeeks.github.io/discourse-composer-tag-layouts/docs/) with just the tables.
> 
https://denvergeeks.github.io/discourse-tag-layouts/
>
> I also use a plugin to provide a Help Popup inside the Composer:  https://github.com/denvergeeks/discourse-plugin-composer-help-button
---

### Tags to Hide Some Thing(s)...

| TAG (You must create the tags!) | HIDES/MODIFIES ELEMENT(S) |
| ------------- | ------------- |
| `hide-all-but-topic-body`  | [hides and modifies all of the below at once]  |
| `hide-header`  | .d-header  |
| `hide-sidebar`  | .sidebar-wrapper  |
| `hide-topic-status`  | .title-wrapper .topic-statuses  |
| `hide-title`  | #topic-title  |
| `hide-avatar`  | .topic-avatar  |
| `hide-author`  | .topic-meta-data.names  |
| `hide-edits`  | div.post-info.edits  |
| `hide-post-date`  | div.post-info.post-date  |
| `hide-read-state`  | .topic-body .read-state  |
| `hide-category`  | .topic-category  |
| `hide-all-meta-data`  | .topic-meta-data  |
| `hide-timeline`  | .topic-navigation.with-timeline  |
| `hide-mobile-topic-progress`  | div#topic-progress  |
| `hide-topic-footer-buttons`  | #topic-footer-buttons  |
| `hide-topic-map`  | div.topic-map  |
| `hide-more-topics`  | div.more-topics__container  |
| `hide-more-content`  | .more-content-wrapper  |
| `hide-suggested-topics-message`  | .suggested-topics-message  |
| `hide-post-links`  | .post-links-container  |
| `hide-main-side-margins`  | [adjusts columns and other widths]  |
| `hide-post-menu-area`  | .post-menu-area  |
| `hide-reactions`  | .discourse-reactions-actions  |
| `hide-copy-link`  | button.widget-button.btn-flat.post-action-menu__copy-link.no-text.btn-icon  |
| `hide-like-button`  | button.widget-button.btn-flat.button-count.like-count.highlight-action.regular-likes.btn-icon-text  |
| `hide-flag-button`  | button.widget-button.btn-flat.create-flag.no-text.btn-icon  |
| `hide-bookmark-button`  | button.widget-button.btn-flat.bookmark.with-reminder.no-text.btn-icon  |
| `hide-reply-button`  | button.widget-button.btn-flat.reply.create.fade-out.btn-icon-text  |
| `hide-signup-cta`  | .signup-cta  |
| `hide-main-padding`  | [removes all padding from _#main-outlet_]  |
| `hide-topic-border-top`  | [removes _border-top_ from _.topic-body_]  |
| `hide-topic-border-bottom`  | [removes _border-top_ from _.topic-status-info, .topic-timer-info_]  |
| `hide-small-action-posts`  | .small-action.onscreen-post  |

| TAG  | HIDES/MODIFIES ELEMENT(S) - OTHER |
| ------------- | ------------- |
| `hide-topic-bg-color`  | [sets _background-color: transparent_ on _#main-outlet_]  |

### Tag Combinations to Hide All But Show Some Thing(s)...

| TAG1 | TAG2  | SHOWS/MODIFIES ELEMENT(S) |
| ------------- | ------------- | ------------- |
| `hide-all-but-topic-body` | `show-timeline` | [Hides Everything But TOC/Topic Timeline] |
| `?` | `?` | [?] |
| `?` | `?` | [?] |

### Tags Specific to a Theme Component or Plugin...

| Theme/Component/Plugin | TAG                          | HIDES/MODIFIES ELEMENT(S)                                       |
| ---------------------- | ---------------------------- | --------------------------------------------------------------- |
| Elegant Theme          | `hide-topic-body-box-shadow` | [removes _box-shadow_ from _.topic-body_ in the Elegant Theme] |
| Header Submenus        | `hide-header-submenus`       | [removes Header Submenus Theme Component]                      |
| Discourse Drawer       | `hide-drawer`                | [removes Discourse Drawer Theme Component]                     |

