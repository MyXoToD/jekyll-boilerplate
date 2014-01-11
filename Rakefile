task :default => [:deploy]

task :build do
  puts "----------"
  puts "Generating current Jekyll build..."
  puts "----------"
  system("jekyll build")
  puts "----------"
  puts "Build ready."
  puts "----------"
  puts ""
  puts ""
end

task :deploy => :build do
  HOST = "" # SSH Host
  USER = "" # SSH Username
  DESTINATION = "" # Absolute path to your destination folder
  SOURCE = "#{Dir.pwd}/_site/" # Local source folder (this should work by default)

  puts "----------"
  puts "Connecting to '#{HOST}' via SSH..."
  puts "Please enter the remote password to start file transfer."
  puts "----------"
  puts ""
  puts ""
  puts "----------"
  system("rsync -avz --delete #{SOURCE} #{USER}@#{HOST}:#{DESTINATION}")
  puts "----------"
  puts ""
  puts ""
  puts "----------"
  puts "File tranfer complete."
  puts "Website is now live: #{HOST}"
  puts "----------"
end

task :jekyll do
  system("jekyll serve --watch")
end

task :compass do
  system("compass watch")
end