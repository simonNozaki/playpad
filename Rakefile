require 'fileutils'
require 'securerandom'

JOTS_DIR = "#{__dir__}/jots"
directory JOTS_DIR

namespace :jots do
  desc 'Create a new jot with the file extension'
  task :new, ['ext'] do |_, args|
    extension = args.ext || 'txt'
    today = Time.now.strftime('%Y%m%d')
    file_name = "#{extension}-#{today}-#{SecureRandom.hex(10)}.#{extension}"
    path = "#{JOTS_DIR}/#{file_name}"

    puts "Create file: #{file_name}"
    File.new path, 'w'
    FileUtils.chmod('+x', path, verbose: true)

    # Visual Studio Codeを外部コマンドで開く
    puts "Open file: #{file_name} with executable"
    system "code #{path}"
  end

  desc 'Delete jots by some condition'
  task :rm, %w[file exts] do |_, args|
    file = args.file
    extension = args.exts
    raise ArgumentError, 'Either file or extension should be specified' if (file.nil? && extension.nil?)

    if file
      FileUtils.rm "#{__dir__}/jots/#{file}"
      return
    end
    if extension
      FileUtils.rm "#{__dir__}/jots/*.#{extension}"
    end
  end
end
