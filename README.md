# Exploit: phishing page

A dynamic phishing page to demonstrate web vulnerabilities such as
[CSRF](https://owasp.org/www-community/attacks/csrf).

## Usage

The phishing website consists of the `index.html`, `script.js` and `script.css`
files. You can serve these as static content with any web server. You can also
simply open the `index.html` file locally.

Configure the page with any combination of the following query parameters:

| Query parameter | Sample value                 | Description                                                      |
| :-------------- | :--------------------------- | :--------------------------------------------------------------- |
| `method`        | `POST`                       | HTML [form method][form-method] to submit the form with          |
| `action`        | `https://example.com/action` | HTML [form action][form-action]                                  |
| `params`        | `foo:bar`                    | Named valued to submit with the form (can be set multiple times) |

Clicking the button displayed on the page will submit a form with this
configuration.

> For example, accessing the page with the following URL and clicking the button
> would submit a `POST` request to `https://example.com/bank/transfer` with the
> parameter `amount` equal to 1000 and the parameter `recipient` equal to
> "h4ck3r":
>
> `file:///path/to/index.html?method=POST&action=https://example.com/bank/transfer&params=amount:1000&params=recipient:h4ck3r`.

[form-action]: https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data#the_method_attribute
[form-method]: https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data#the_method_attribute
