source "https://rubygems.org"

# Use GitHub Pages gem — this pins all dependencies to
# the versions GitHub Pages actually supports.
gem "github-pages", group: :jekyll_plugins

# Windows/JRuby only
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for watching files on Windows
gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` gem to a compatible version in JRuby builds
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
