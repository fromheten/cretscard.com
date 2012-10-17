# encoding: UTF-8
# Ok, this is my first attempt at a Rake. 

desc "Makes a new post. First asks for title, and then opens your editor. You only have to write and :x, and it is done"
task :new_article do
	# Should get title and date, create a .md in source/posts
	puts "What is the title of your post?"
	title = $stdin.gets.delete("\n")

	date = "#{Date.today.to_s}-"
	
	title_formatted_for_nanoc_compilation_compliance = title.downcase.gsub(/\s/, '_').gsub(/#/,'')

	filename = date + title_formatted_for_nanoc_compilation_compliance

	the_file = "./content/blog/#{filename}.markdown"
	puts "The raw file for your post if located in " + the_file

	post_structure = "---\nkind: article\nlayout: post\ntitle: \"#{title}\"\ndate: #{date} #{Time.now.hour}:#{Time.now.min}\ncomments: true\ncategories: \n---\n\n"
	
	# Write the post structure and then open it in default editor
	File.open(the_file, 'w').write(post_structure)
	
	puts "Have a pleasant day, and don't write nothing stupid"
	# Here is where you edit what editor you like
	system "mvim -c 'norm G' #{the_file}"
end
