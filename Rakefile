namespace :book do
  desc 'build basic book formats'
  task :build do
    puts "Converting to HTML..."
    `bundle exec asciidoctor busting-myths.adoc`
    puts " -- HTML output at busting-myths.html"

    puts "Converting to DocBook..."
    `bundle exec asciidoctor -d book -b docbook5 busting-myths.adoc -o busting-myths.docbook`
    puts " -- DocBook output at busting-myths.docbook"

    puts "Converting to EPub..."
    `pandoc -f docbook -t epub busting-myths.docbook -o busting-myths.epub`
    puts " -- DocBook output at busting-myths.docbook"

  end
end

task :default => "book:build"
