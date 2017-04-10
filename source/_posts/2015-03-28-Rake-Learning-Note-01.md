title: Rake Learning Note 01
thumbnail: /img/ruby.jpg
date: 2015-03-28 12:07:00
tags: ruby
categories: Technical
---

## Rake basic

This `rake task` will convert .md file to .html use `pandoc`,
and will not complied the unmodified file again.

``` ruby
task :default => :html
task :html => %W[ch1.html ch2.html ch3.html]

%W[ch1.md ch2.ms ch3.md].each do |md_file|
  html_file = File.basename(md_file, '.md') + '.html'
  file html_file => md_file do
    sh "pandoc -o #{html_file} #{md_file}"
  end
end
```
<!--more-->

### Use `rule` to simplify

``` ruby

task :default => :html
task :html => %W[ch1.html ch2.html ch3.html]

rule ".html" => ".md" do |t|
  sh "pandoc -o #{t.name} #{t.source}"
end

```


### More flexible with `Rake::FileList`

```ruby
source_files = Rake::FileList.new("**/*.md", "**/*.markdown") do |fl|
  fl.exclude("~*")
  fl.exclude(/^scratch\//)
  fl.exclude do |f|
    `git ls-files #{f}`.empty?
  end
end

task :default => :html
task :html => source_files.ext(".html")

rule ".html" => ".md" do |t|
  sh "pandoc -o #{t.name} #{t.source}"
end

rule ".html" => ".markdown" do |t|
  sh "pandoc -o #{t.name} #{t.source}"
end
```

### A useful trick to debug rake error

Add this line into top of rake file

```ruby
Rake.application.options.trace_rules = true
```

### Make the rule more general

```ruby
SOURCE_FILES = Rake::FileList.new("**/*.md", "**/*.markdown") do |fl|
  fl.exclude("~*")
  fl.exclude(/^scratch\//)
  fl.exclude do |f|
    `git ls-files #{f}`.empty?
  end
end

task :default => :html
task :html => SOURCE_FILES.ext(".html")

rule ".html" => ->(f){source_for_html(f)} do |t|
  sh "pandoc -o #{t.name} #{t.source}"
end

def source_for_html(html_file)
  SOURCE_FILES.detect{|f| f.ext('') == html_file.ext('')}
end
```

