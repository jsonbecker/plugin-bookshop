# plugin-bookshop
A Bookshop affiliate plugin for Micro.blog that can be used by other Hugo sites

## Description
[Bookshop](https://bookshop.org) is an online bookstore connected to independent book sellers across the country. They have an easy to sign up for affiliate program that you can use to earn some money when someone buys a book after clicking on a link you provide.

This plugin provides a [Hugo shortcode](https://gohugo.io/content-management/shortcodes/) for your Micro.blog (this can be easily used with other Hugo blogs as well) that makes it easy to add affiliate links and widgest from Bookshop to your site.

## Usage

Using shortcodes are easy. They have a special delimiter, but otherwise, look a lot like HTML. The simplest version of Bookshop works like this:

```html
{{< bookshop 9781524760380 >}} Shorefall by Robert Jackson Bennett {{< /bookshop >}}
```

Using the affiliate ID setup in your Micro.blog plugin, this will produce the following HTML

```html
<a href="https://bookshop.org/a/1234/9781524760380">Shorefall by Robert Jackson Bennett</a>
```

In the example above, 1234 is a fake affiliate id-- you ID will be there.

You can also use the Bookshop.org widgets. This requires a little more work, and can be called like so:

```html
{{< bookshop 9781524760380 book >}} 
```

or

```html
{{< bookshop 9781524760380 book_button >}} 
```

Which will turn into the `book` or `book_button` widgets they offer with the correct embed code. 

You can also use named parameters, of which there are two:

- `isbn` which is the ISBN number used as the "sku" of the book to generate the link
- `type` which indicates which embed, book or book_button you want.

When not specifying the `type` by name or as the second parameter, you must wrap the link text you want to use in this shortcode or nothing will appear on your site.

### Lists

Bookshop now supports list widgets. After considering overloading the `bookshop` shortcode with a `type="list"`, I decided to support this with a separate shortcode. This way the `bookshop` shortcode always supports widgets related to a single book. With this new shortcode, you only need to supply the slug for your list:

```html
{{< bookshoplist read-2022-a28bc91a-fc4a-4573-bfa4-15c42345ca33 >}}
```
