namespace :book do
  desc 'build basic book formats'
  task :build do
    puts "Converting to HTML..."
    `bundle exec asciidoctor busting-myths.adoc`
    puts " -- HTML output at busting-myths.html"

    puts "Converting to EPub..."
    `bundle exec asciidoctor-epub3 busting-myths.adoc`
    puts " -- Epub output at busting-myths.epub"

    puts "Converting to Mobi (kf8)..."
    `bundle exec asciidoctor-epub3 -a ebook-format=kf8 busting-myths.adoc`
    puts " -- Mobi output at busting-myths.mobi"

    puts "Converting to PDF... (this one takes a while)"
    `bundle exec asciidoctor-pdf busting-myths.adoc 2>/dev/null`
    puts " -- PDF output at busting-myths.pdf"
  end
end

task :default => "book:build"
