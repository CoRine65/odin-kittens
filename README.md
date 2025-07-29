# Odin Kittens Api

This is an API-only Rails app that manages kitten data with attributes like name, age, cuteness, and softness.

Based on Odin Project's: https://www.theodinproject.com/lessons/ruby-on-rails-kittens-api

Steps to accomplish this app:

1. initiated a git repository
    - cloned it to the designated folder
2. initiated new rails Kitten app
    - updated README
--commit 1--
3. Created kitten model with attributes: name, age, cuteness and softness
4. Created Kitten controller with all RESTful actions 
    - :kittens routes with RESTful actions
    - set routes
--commit 2--
5. update the kitten controller with the right restful action methods
    - set up views 
        - index, new, edit, show
    - created a form partials
    - added flash messages: remember to add display to the application.html
6. Testing
    - Error: can't find partial
        - cause: typo missing _ in _form
    - Error: delete does not delete
        - cause:  @rails/ujs is not properly loaded, so Rails’ JavaScript helpers for method: :delete, data-confirm, don’t work.
        - fix: Make sure @rails/ujs is pinned correctly in config/importmap.rb and started in application.js
    - Error: importmap integrity mismatch
        - cause: The integrity hash for the downloaded file doesn't match what’s listed in your importmap file. This can happen because/after: 
            Manually editing the importmap
            Rails upgrading/changing asset versions
            Corrupted or outdated asset files
        - fix: re-pin the package
7. JSON API
    - Error: KittensController does not support JSON 
        - fix: added respond_to, to index on kittens_controller