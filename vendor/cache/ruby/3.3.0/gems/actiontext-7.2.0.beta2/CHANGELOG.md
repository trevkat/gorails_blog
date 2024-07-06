## Rails 7.2.0.beta2 (June 04, 2024) ##

*   Sanitize ActionText HTML ContentAttachment in Trix edit view
    [CVE-2024-32464]


## Rails 7.2.0.beta1 (May 29, 2024) ##

*   Use `includes` instead of `eager_load` for `with_all_rich_text`.

    *Petrik de Heus*

*   Delegate `ActionText::Content#deconstruct` to `Nokogiri::XML::DocumentFragment#elements`.

    ```ruby
    content = ActionText::Content.new <<~HTML
      <h1>Hello, world</h1>

      <div>The body</div>
    HTML

    content => [h1, div]

    assert_pattern { h1 => { content: "Hello, world" } }
    assert_pattern { div => { content: "The body" } }
    ```

    *Sean Doyle*

*   Fix all Action Text database related models to respect
    `ActiveRecord::Base.table_name_prefix` configuration.

    *Chedli Bourguiba*

*   Compile ESM package that can be used directly in the browser as actiontext.esm.js

    *Matias Grunberg*

*   Fix using actiontext.js with Sprockets.

    *Matias Grunberg*

*   Upgrade Trix to 2.0.7

    *Hartley McGuire*

*   Fix using Trix with Sprockets.

    *Hartley McGuire*

Please check [7-1-stable](https://github.com/rails/rails/blob/7-1-stable/actiontext/CHANGELOG.md) for previous changes.
