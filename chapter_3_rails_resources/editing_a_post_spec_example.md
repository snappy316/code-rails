# Editing an article spec example
```ruby
require "test_helper"

feature "Editing an Article" do
  scenario "submit updates to an existing article" do
    # Given an existing article
    article = Article.create(title: "Becoming a Code Fellow", body: "Means striving for excellence.")
    visit article_path(article)

    # When I click edit and submit changed data
    click_on "Edit"
    fill_in "Title", with: "Becoming a Web Developer"
    click_on "Update Article"

    # Then the article is updated
    page.text.must_include "Article was successfully updated"
    page.text.must_include "Web Developer"
  end
end
```
