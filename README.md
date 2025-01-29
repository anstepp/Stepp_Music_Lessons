# Aaron Stepp Music Lessons

This repo hosts the code for Aaron Stepp's music lessons site.

## Develop locally

1. Build the Docker container.
   ```
   cd docker/
   ./build.sh
   ```

2. Return to repo root.

3. Start the Docker container.
   ```
   docker run -it --rm -p 4000:4000 -p 35729:35729 -v ./site:/site jekylldev bash
   ```

4. Inside the Docker container, run jekyll in live reload mode.
   ```
   cd /site && bundle install && bundle update && bundle exec jekyll serve --livereload --host 0.0.0.0
   ```

5. Open the site in a web browser.
   ```
   http://localhost:4000/Stepp_Music_Lessons/
   ```

6. Edit the markdown code in `_pages/` to update content.