# Errors

<aside class="notice">
This error section is stored in a separate file in <code>includes/_errors.md</code>. Slate allows you to optionally separate out your docs into many files...just save them to the <code>includes</code> folder and add them to the top of your <code>index.md</code>'s frontmatter. Files are included in the order listed.
</aside>

The Kittn API uses the following error codes:


Error Code | Meaning
---------- | -------
200 | OK |Everything is OK. 
400 | Bad Request -- Your request is invalid. See errors attached.
401 | Unauthorized -- Your API key is wrong.
402 | Payment Required -- You don't have enough credit to send the message.
