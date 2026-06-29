require 'rake'

task :default do
  puts "Run 'rake help' to see available tasks."
end

desc 'Download CSV file from github repo'
task :csv do
  require 'open-uri'
  require 'fileutils'

  url   = 'https://raw.githubusercontent.com/ticha-zapotec/digital-text-explorer-data/refs/heads/main/csv/documents.csv'
  dest  = 'src/documents.csv'

  FileUtils.mkdir_p('src') unless Dir.exist?('src')

  puts "Downloading CSV file from #{url} to #{dest}..."
  URI.open(url) do |remote_file|
    File.open(dest, 'wb') do |local_file|
      local_file.write(remote_file.read)
    end
  end
  puts "Download complete."
end